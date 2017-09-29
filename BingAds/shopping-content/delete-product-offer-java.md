---
title: "Deleting a Product Offer in Java"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "scottwhi"
---
# Deleting a Product Offer in Java
This example shows how to delete a single product offer using Java. For information about deleting product offers, see [Deleting a product offer from the store](../shopping-content/manage-products.md#delete).

For simplicity, the example hard codes the access token used to authenticate the user.

```java
package products.capi.microsoft.com;

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

// Uses Jackson to serialize and deserialize JSON.

import com.fasterxml.jackson.databind.ObjectMapper;


class ProductsEx {

	// Jackson object used to serialize and deserialize JSON.

	private static ObjectMapper jsonMapper = new ObjectMapper();

	private static String accessToken = "<accesstokengoeshere>"; 
	public static String devToken = "<devtokengoeshere>"; 

    // URI templates used to get resources.
    
    public static final String BaseUri = "https://content.api.bingads.microsoft.com/shopping/v9.1";
    public static final String BmcUri = BaseUri + "/bmc/%d";
    public static final String DeleteUri = BmcUri + "/products/%s";

    // Query strings. 
    
    public static final String queryString = "?alt=json";

    // Replace with your ID.
    
    public static long merchantId = <merchantidgoeshere>; 

    // Replace with the ID of the product offer to delete.

    public static String productId = "Online:EN:US:X_0123";

	// This example shows how to delete a single product offer.
  
	public static void main(String[] args) {

		try {
			Map\<String, String> headers = getCredentialHeaders();

            String url = String.format(DeleteUri + queryString, merchantId, productId);

            // Delete the specified product.

            deleteResource(url, headers);

      		System.out.println("Deleted product: " + productId);
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

  // Deletes the specified product offer.
  
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
        		
    			if (statusCode == HttpURLConnection.HTTP_BAD_REQUEST) {
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
