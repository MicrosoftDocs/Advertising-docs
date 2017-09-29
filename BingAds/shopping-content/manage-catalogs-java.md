---
title: "Managing Catalogs in Java"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "scottwhi"
---
# Managing Catalogs in Java
This example shows how to manage your store's catalogs using Java. For information about the catalog-related classes used by this example, see [Catalogs](../shopping-content/catalogs-resource.md#catalogs) and [Catalog](../shopping-content/catalogs-resource.md#catalog). For information about working with catalogs, see [Managing your Catalogs](../shopping-content/manage-catalogs.md).

For simplicity, the example hard codes the access token used to authenticate the user.

```java
package catalogs.capi.microsoft.com;

import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStreamWriter;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.net.HttpURLConnection;
import java.net.URL;
import java.util.ArrayList;
import java.util.List;
import java.util.Map;
import java.util.HashMap;
import java.util.Map.Entry;

// Uses Jackson to serialize and deserialize JSON.

import com.fasterxml.jackson.core.JsonParseException;
import com.fasterxml.jackson.databind.JsonMappingException;
import com.fasterxml.jackson.databind.ObjectMapper;
import com.fasterxml.jackson.annotation.*;
import com.fasterxml.jackson.annotation.JsonInclude.Include;


class Catalogs {

	// Jackson object used to serialize and deserialize JSON.

	private static ObjectMapper jsonMapper = new ObjectMapper();

	private static String accessToken = "<accesstokengoeshere>"; 
    public static String devToken = "<devtokengoeshere>"; 

    // URI templates used to get resources.
    
    public static final String BaseUri = "https://content.api.bingads.microsoft.com/shopping/v9.1";
    public static final String BmcUri = BaseUri + "/bmc/%d";
    public static final String CatalogsUri = BmcUri + "/catalogs";
    public static final String CatalogUri = CatalogsUri + "/%d";


    // Replace with your store ID.
    
    public static long merchantId = <merchantidgoeshere>; 

	// This example shows how to list, add, update, and delete
    // catalogs in the store.
    
	public static void main(String[] args) throws JsonParseException, JsonMappingException, IOException {

		try {
			Map\<String, String> headers = getCredentialHeaders();

            String url = String.format(CatalogsUri, merchantId);

            // Get and print the current list of catalogs.

            CatalogCollection collection = (CatalogCollection) getResource(url, headers, CatalogCollection.class);
            printCatalogs(collection);

            // Add a couple of catalogs.

            List<Catalog> addedCatalogs = addCatalogs(url, headers);

            // Get and print the current list of catalogs.

            collection = (CatalogCollection) getResource(url, headers, CatalogCollection.class);
            printCatalogs(collection);

            // Update the first catalog that we added
            // to enable it for publishing. When you update the 
            // catalog, you must specify both Name and IsPublishingEnabled.

            System.out.println("*** Updating Catalog ***\n");
            String catalogUrl = String.format(CatalogUri, merchantId, ((Catalog) addedCatalogs.toArray()[0]).getId());
            Catalog catalog = new Catalog();
            catalog.setName(((Catalog) addedCatalogs.toArray()[0]).getName());
            catalog.setIsPublishingEnabled(true);

            updateResource(catalogUrl, headers, catalog);

            // Get and print the updated catalog.

            Catalog updatedCatalog = (Catalog) getResource(catalogUrl, headers, Catalog.class);
            printCatalogDetails(updatedCatalog);

            // Delete the catalogs that we created.

            deleteCatalogs(CatalogUri, headers, merchantId, addedCatalogs);

            // Get and print the current list of catalogs.

            collection = (CatalogCollection) getResource(url, headers, CatalogCollection.class);
            printCatalogs(collection);
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
    		char[] buffer = new char[2048];
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


    // Adds a Catalog to the store.
    
    private static Catalog addResource(String uri, Map\<String, String> headers, Catalog catalog) throws IOException, CapiException 
    {
    	HttpURLConnection connection = null;
    	URL url;
    	InputStream istream = null;
    	OutputStreamWriter ostream = null;
    	BufferedReader reader = null;
    	Catalog catalogOut = null;

    	try {
        	String json = jsonMapper.writeValueAsString(catalog);

    		url = new URL(uri);
    		connection = (HttpURLConnection) url.openConnection();

    		connection.setRequestMethod("POST");
    		connection.setRequestProperty("Content-Type", "application/json");
    		connection.setRequestProperty("Content-Length", String.valueOf(json.length()));

    		for (Entry\<String, String> header : headers.entrySet())
    		{
    			connection.setRequestProperty(header.getKey(), header.getValue());
    		}

    		connection.setDoInput(true);
    		connection.setDoOutput(true);
    		connection.setUseCaches(false);

    		ostream = new OutputStreamWriter(connection.getOutputStream());
    		ostream.write(json);
    		ostream.close();

    		int statusCode = connection.getResponseCode();
    		
    		if (statusCode >= HttpURLConnection.HTTP_BAD_REQUEST) {
        		istream = connection.getErrorStream();
    		}
    		else {
        		istream = connection.getInputStream();
    		}
 
    		StringBuffer response = new StringBuffer();
    		reader = new BufferedReader(new InputStreamReader(istream));
    		char[] buffer = new char[2048];
    		int len = 0;
    		
    		while ((len = reader.read(buffer)) != -1) {
    			response.append(new String(buffer, 0, len));
    		}

    		System.out.println(response);
    		
    		if (statusCode >= HttpURLConnection.HTTP_BAD_REQUEST) {
    			if (statusCode < HttpURLConnection.HTTP_INTERNAL_ERROR) {
    	    		ContentError errors = jsonMapper.readValue(response.toString(), ContentError.class);
    				throw new CapiException("Batch request failed.\n", errors.getError().getErrors());
    			}
    			else {
    				throw new CapiException(response.toString());
    			}
    		}

    		catalogOut = jsonMapper.readValue(response.toString(), Catalog.class);
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

    		if (ostream != null) {
    			ostream.close();
    		}
    	}

    	return catalogOut;
    }

    // Updates a Catalog in the store.
    
    private static Catalog updateResource(String uri, Map\<String, String> headers, Catalog catalog) throws IOException, CapiException 
    {
    	HttpURLConnection connection = null;
    	URL url;
    	InputStream istream = null;
    	OutputStreamWriter ostream = null;
    	BufferedReader reader = null;
    	Catalog catalogOut = null;

    	try {
        	String json = jsonMapper.writeValueAsString(catalog);

    		url = new URL(uri);
    		connection = (HttpURLConnection) url.openConnection();

    		connection.setRequestMethod("PUT");
    		connection.setRequestProperty("Content-Type", "application/json");
    		connection.setRequestProperty("Content-Length", String.valueOf(json.length()));

    		for (Entry\<String, String> header : headers.entrySet())
    		{
    			connection.setRequestProperty(header.getKey(), header.getValue());
    		}

    		connection.setDoInput(true);
    		connection.setDoOutput(true);
    		connection.setUseCaches(false);

    		ostream = new OutputStreamWriter(connection.getOutputStream());
    		ostream.write(json);
    		ostream.close();

    		int statusCode = connection.getResponseCode();
    		
    		if (statusCode >= HttpURLConnection.HTTP_BAD_REQUEST) {
        		istream = connection.getErrorStream();
    		}
    		else {
        		istream = connection.getInputStream();
    		}
 
    		StringBuffer response = new StringBuffer();
    		reader = new BufferedReader(new InputStreamReader(istream));
    		char[] buffer = new char[2048];
    		int len = 0;
    		
    		while ((len = reader.read(buffer)) != -1) {
    			response.append(new String(buffer, 0, len));
    		}

    		System.out.println(response);
    		
    		if (statusCode >= HttpURLConnection.HTTP_BAD_REQUEST) {
    			if (statusCode < HttpURLConnection.HTTP_INTERNAL_ERROR) {
    	    		ContentError errors = jsonMapper.readValue(response.toString(), ContentError.class);
    				throw new CapiException("Batch request failed.\n", errors.getError().getErrors());
    			}
    			else {
    				throw new CapiException(response.toString());
    			}
    		}

    		catalogOut = jsonMapper.readValue(response.toString(), Catalog.class);
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

    		if (ostream != null) {
    			ostream.close();
    		}
    	}

    	return catalogOut;
    }

    // Deletes a Catalog from the store.
    
    private static void deleteResource(String uri, Map\<String, String> headers) throws IOException, CapiException 
    {
    	HttpURLConnection connection = null;
    	URL url;
    	InputStream istream = null;
    	BufferedReader reader = null;


    	try {
    		url = new URL(uri);
    		connection = (HttpURLConnection) url.openConnection();

    		connection.setRequestMethod("DELETE");
    		connection.setRequestProperty("Accept", "application/json");

    		for (Entry\<String, String> header : headers.entrySet())
    		{
    			connection.setRequestProperty(header.getKey(), header.getValue());
    		}

    		connection.setUseCaches(false);

    		int statusCode = connection.getResponseCode();
    		
    		if (statusCode >= HttpURLConnection.HTTP_BAD_REQUEST) {
    			istream = connection.getErrorStream();

        		StringBuffer response = new StringBuffer();
        		reader = new BufferedReader(new InputStreamReader(istream));
        		char[] buffer = new char[2048];
        		int len = 0;
        		
        		while ((len = reader.read(buffer)) != -1) {
        			response.append(new String(buffer, 0, len));
        		}

        		System.out.println(response);
        		
    			if (statusCode < HttpURLConnection.HTTP_INTERNAL_ERROR) {
    	    		ContentError errors = jsonMapper.readValue(response.toString(), ContentError.class);
    				throw new CapiException("Batch request failed.\n", errors.getError().getErrors());
    			}
    			else {
    				throw new CapiException(response.toString());
    			}
    		}
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
    }

    // Creates a couple of catalogs and adds them 
    // to the store.
    
    private static List<Catalog> addCatalogs(String url, Map\<String, String> headers) throws IOException, CapiException
    {
    	List<Catalog> catalogs = new ArrayList<Catalog>();

        System.out.println("*** Adding Catalogs ***\n");

        // This catalog is not enabled for publishing.

        Catalog catalog = new Catalog();
        catalog.setName("Mens Apparel");
        catalog.setMarket("en-US");
        catalog.setIsPublishingEnabled(false);

        catalogs.add(addResource(url, headers, catalog));

        // This catalog is enabled for publishing.

        catalog = new Catalog();
        catalog.setName("Womens Apparel");
        catalog.setMarket("en-US");
        catalog.setIsPublishingEnabled(true);

        catalogs.add(addResource(url, headers, catalog));

        return catalogs;
    }

    // Deletes the specified catalogs from the store.
    
    private static void deleteCatalogs(String uri, Map\<String, String> headers, long merchantId, List<Catalog> catalogs) throws Exception
    {
        System.out.println("*** Deleting Catalogs ***\n");

        for (Catalog catalog : catalogs)
        {
            // Build the endpoint URL.

            String url = String.format(uri, merchantId, catalog.getId());

            // Delete the catalog from the store.

            deleteResource(url, headers);
            System.out.println("Deleted catalog: " + catalog.getId());
        }

        System.out.println();
    }

    
    
    // Prints the list of catalogs

    private static void printCatalogs(CatalogCollection collection)
    {
        System.out.println("There are " + collection.getCatalogs().size() + " catalogs.\n");

        for (Catalog catalog : collection.getCatalogs())
        {
            printCatalogDetails(catalog);
        }
    }

    // Print catalog details.

    private static void printCatalogDetails(Catalog catalog)
    {
    	System.out.println("Name: " + catalog.getName());
    	System.out.println("ID: " + catalog.getId());
    	System.out.println("Market: " + catalog.getMarket());
    	System.out.println("IsDefault: " + catalog.getIsDefault());
    	System.out.println("IsPublishingEnabled: " + catalog.getIsPublishingEnabled());
    	System.out.println();
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

// The following define the Catalog classes.

@JsonInclude(Include.NON_DEFAULT)
class Catalog
{
	private long id;
	private String name;
	private String market;
    //@JsonDeserialize(using=StringBooleanDeserializer.class)
	private Boolean isPublishingEnabled;
    //@JsonDeserialize(using=StringBooleanDeserializer.class)
	private Boolean isDefault;
	
    public long getId() { return this.id; }
    public void setId(long value) { this.id = value; }

    public String getName() { return this.name; }
    public void setName(String value) { this.name = value; }

    public String getMarket() { return this.market; }
    public void setMarket(String value) { this.market = value; }

    public Boolean getIsPublishingEnabled() { return this.isPublishingEnabled; }
    public void setIsPublishingEnabled(Boolean value) { this.isPublishingEnabled = value; }

    public Boolean getIsDefault() { return this.isDefault; }
    public void setIsDefault(Boolean value) { this.isDefault = value; }
}

class CatalogCollection
{
	private List<Catalog> catalogs;
	
    public List<Catalog> getCatalogs() { return this.catalogs; }
    public void setCatalogs(List<Catalog> value) { this.catalogs = value; }
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
