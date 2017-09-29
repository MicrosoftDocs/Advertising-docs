---
title: "Downloading a Catalog Status Report in Java"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "scottwhi"
---
# Downloading a Catalog Status Report in Java
This example shows how to get a report that shows whether products were successfully added to the catalog. For information about the class used by this example, see [Status](../shopping-content/status-resource.md#status). For information about getting the report, see [How Do I Get the Status of Product Offers?](../shopping-content/how-get-status-product-offers.md)

For simplicity, the example hard codes the access token used to authenticate the user.

```java
package status.capi.microsoft.com;

import java.io.BufferedInputStream;
import java.io.BufferedOutputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.net.HttpURLConnection;
import java.net.URL;
import java.util.List;
import java.util.Map;
import java.util.HashMap;
import java.util.Map.Entry;
import java.util.regex.Pattern;
import java.util.zip.*;
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;

// Uses Jackson to serialize and deserialize JSON.

import com.fasterxml.jackson.core.JsonParseException;
import com.fasterxml.jackson.databind.JsonMappingException;
import com.fasterxml.jackson.databind.ObjectMapper;


class Catalogs {

	// Jackson object used to serialize and deserialize JSON.

	private static ObjectMapper jsonMapper = new ObjectMapper();

	private static String accessToken = "<accesstokengoeshere>"; 
    public static String devToken = "<devtokengoeshere>"; 

    // URI templates used to get resources.
    
    public static final String BaseUri = "https://content.api.bingads.microsoft.com/shopping/v9.1";
    public static final String BmcUri = BaseUri + "/bmc/%d";
    public static final String StatusUri = BmcUri + "/catalogs/%d/status";


    // Replace with your IDs.
    
    public static long merchantId = <merchantidgoeshere>; 
    public static long catalogId = <catalogidgoeshere>;

    // The path where the uncompressed report is written to.

    public static String downloadPath = "c:\\reports\\";


	// Gets the status of the products in the specified catalog. If any
    // of the products failed editorial review, the example downloads
    // the report.
    
	public static void main(String[] args) throws JsonParseException, JsonMappingException, IOException {

		try {
			Map\<String, String> headers = getCredentialHeaders();

            String url = String.format(StatusUri, merchantId, catalogId);
            
            // Get the catalog's status.

            CatalogStatus status = (CatalogStatus) getResource(url, headers, CatalogStatus.class);

            // Prints the status and downloads the report.
            
            printCatalogStatus(status, catalogId);
            System.out.println();
		}
		catch (CapiException e) {
			if (e.getErrors() != null){
	    		printErrors(e.getErrors());
			}
			else
			{
				System.out.println(e.getMessage());
			}
		}
    	catch (IOException e) {
    		System.out.println(e.getMessage());
    	}
		catch (Exception e) {
			System.out.println("\n" + e.getMessage());
		}

	}


	// Get tokens for the authentication headers.
	
    private static Map\<String, String> getCredentialHeaders()
    {
        // TODO: Add logic to get the user's OAuth token. 

        Map\<String, String> headers = new HashMap\<String, String>();
        headers.put("AuthenticationToken", accessToken);
        headers.put("DeveloperToken", devToken);

        return headers;
    }
    

    // Generic method to get a resource from the specified URL.
    
    private static Object getResource(String uri, Map\<String, String> headers, Class\<?> type) throws IOException, CapiException 
    {
    	Object resource = null;
    	HttpURLConnection connection = null;
    	URL url;
    	InputStream istream = null;
    	BufferedReader reader = null;
    	final int BUFFER_SIZE = 2048;

    	try {
    		url = new URL(uri);
    		connection = (HttpURLConnection) url.openConnection();

    		connection.setRequestMethod("GET");
    		connection.setRequestProperty("Accept", "application/json");

    		for (Entry\<String, String> header : headers.entrySet())
    		{
    			connection.setRequestProperty(header.getKey(), header.getValue());
    		}

    		connection.setUseCaches(false);

    		int statusCode = connection.getResponseCode();
    		
    		if (statusCode >= HttpURLConnection.HTTP_BAD_REQUEST) {
    			istream = connection.getErrorStream();
    		}
    		else {
    			istream = connection.getInputStream();
    		}
 
    		StringBuffer response = new StringBuffer();
    		reader = new BufferedReader(new InputStreamReader(istream));
    		char[] buffer = new char[BUFFER_SIZE];
    		int len = 0;
    		
    		while ((len = reader.read(buffer)) != -1) {
    			response.append(new String(buffer, 0, len));
    		}

    		System.out.println(response);
    		
    		
    		if (statusCode >= HttpURLConnection.HTTP_BAD_REQUEST) {
    			if (statusCode == HttpURLConnection.HTTP_BAD_REQUEST) {
    	    		ContentError errors = jsonMapper.readValue(response.toString(), ContentError.class);
    				throw new CapiException("Batch request failed.\n", errors.getError().getErrors());
    			}
    			else {
    				throw new CapiException(response.toString());
    			}
    		}

    		resource = jsonMapper.readValue(response.toString(), type);
    	}
    	finally {
    		if (connection != null) {
    			connection.disconnect();
    		}

    		if (reader != null) {
    			reader.close();
    		}

    		if (istream != null) {
    			istream.close();
    		}
    	}

    	return resource;
    }

    // Prints the catalog's status. If a product failed review,
    // downloads the rejection report.
    
    private static void printCatalogStatus(CatalogStatus status, long catalogId) throws IOException, CapiException
    {
        System.out.printf("Catalog %d Status Report\n", catalogId);
        System.out.println("Published offers: " + status.getPublishedCount());
        System.out.println("Rejected offers: " + status.getRejectedCount());

        if (status.getRejectedCount() > 0)
        {
            String reportPath = getRejectionReport(status.getRejectionReportUrl());
            System.out.println("Report was written to " + reportPath);
        }
    }


    // Gets the rejection report. The report is 
    // named MerchantCatalogReport.csv.
    
    private static String getRejectionReport(String url) throws IOException, CapiException
    {
        return downloadReport(url, downloadPath);
    }


    // Downloads the rejection report and writes
    // it to the specified path.
    
    private static String downloadReport(String uri, String path) throws IOException, CapiException
    {
    	HttpURLConnection connection = null;
    	URL url;
    	InputStream istream = null;
    	BufferedReader reader = null;
    	ZipInputStream zipIStream = null;
    	BufferedOutputStream dest = null;
    	String downloadFilePath = null;
    	final int BUFFER_SIZE = 2048;

    	try {
    		url = new URL(uri);
    		connection = (HttpURLConnection) url.openConnection();
    		connection.setRequestMethod("GET");
    		connection.setRequestProperty("Accept", "application/zip");
    		connection.setUseCaches(false);

    		int statusCode = connection.getResponseCode();

    		StringBuffer response = new StringBuffer();

    		if (statusCode >= HttpURLConnection.HTTP_BAD_REQUEST) {
    			istream = connection.getErrorStream();
        		reader = new BufferedReader(new InputStreamReader(istream));
        		char[] buffer = new char[2048];
        		int len = 0;
        		
        		while ((len = reader.read(buffer)) != -1) {
        			response.append(new String(buffer, 0, len));
        		}

				throw new CapiException(response.toString());
			}
    		
   			istream = connection.getInputStream();
    		zipIStream = new ZipInputStream(new BufferedInputStream(istream));
    		
    		// Build the download path.
    		
    		String filename = zipIStream.getNextEntry().getName();
    		String filenameParts[] = filename.split(Pattern.quote("."));
    		DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyyMMddhhmmss");
    		String timestamp = LocalDateTime.now().format(formatter);
    		downloadFilePath = path + filenameParts[0] + "_" + timestamp + "." + filenameParts[1];

    		// The download file is ZIP compressed. Uncompress the 
    		// file and write it to the download path.
    		
			System.out.println("\nExtracting: " + filename);
			int len;
			byte buffer[] = new byte[BUFFER_SIZE];
			FileOutputStream ostream = new FileOutputStream(downloadFilePath);
			dest = new BufferedOutputStream(ostream, BUFFER_SIZE);
			
			while ((len = zipIStream.read(buffer,  0, BUFFER_SIZE)) != -1) {
				dest.write(buffer, 0, len);
			}
			dest.flush();
    	}
    	finally {
			if (connection != null) {
				connection.disconnect();
			}
	
			if (reader != null) {
				reader.close();
			}
			
			if (istream != null) {
				istream.close();
			}
			
			if (zipIStream != null) {
				zipIStream.close();
			}
			
			if (dest != null) {
				dest.close();
			}
		}
    	
    	return downloadFilePath;
    }
    
    
    // Print errors.
    
    private static void printErrors(List<Error> errors)
    {
        for (Error error : errors)
        {
            System.out.printf("reason: %s\nmessage: %s\ndomain: %s\n\n",
                error.getReason(), error.getMessage(), error.getDomain());
        }
    }

}


@SuppressWarnings("serial")
class CapiException extends Exception {

	private List<Error> errors = null;
	
	public CapiException(String message) {
		super(message);
	}

	public CapiException(String message, List<Error> errors) {
		super(message);
		this.errors = errors;
	}

	public CapiException(Throwable cause) {
		super(cause);
	}

	public CapiException(String message, Throwable cause) {
		super(message, cause);
	}
	
	public List<Error> getErrors() { return this.errors; }
	public void setErrors(List<Error> value) { this.errors = value; }
}


// Reporting classes.

class CatalogStatus
{
	private long catalogId;
	private long publishedCount;
	private long rejectedCount;
	private String rejectionReportUrl;
	
    public long getCatalogId() { return this.catalogId; }
    public void setCatalogId(long value) { this.catalogId = value; }

    public long getPublishedCount() { return this.publishedCount; }
    public void setPublishedCount(long value) { this.publishedCount = value; }

    public long getRejectedCount() { return this.rejectedCount; }
    public void setRejectedCount(long value) { this.rejectedCount = value; }

    public String getRejectionReportUrl() { return this.rejectionReportUrl; }
    public void setRejectionReportUrl(String value) { this.rejectionReportUrl = value; }
}


//Classes used to handle errors.

class Error
{
	private String location;
	private String locationType;
	private String domain;
	private String message;
	private String reason;
	
public String getLocation() { return this.location; }

public String getLocationType() { return this.locationType; }

public String getDomain() { return this.domain; }

public String getMessage() { return this.message; }

public String getReason() { return this.reason; }
}

class ErrorCollection
{
	private List<Error> errors;
	
public List<Error> getErrors() { return this.errors; }
}


class ContentError
{
	private ErrorCollection error;
	
public ErrorCollection getError() { return this.error; }
}
```
