---
title: "Getting a Product Offer in Java"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "scottwhi"
---
# Getting a Product Offer in Java
This example shows how to get a single product offer using Java. For information about the class used by this example, see [Product](../shopping-content/products-resource.md#product). For information about getting product offers, see [Getting a product offer from the store](../shopping-content/manage-products.md#get).

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

//Uses Jackson to serialize and deserialize JSON.

import com.fasterxml.jackson.core.JsonParser;
import com.fasterxml.jackson.core.JsonProcessingException;
import com.fasterxml.jackson.databind.DeserializationContext;
import com.fasterxml.jackson.databind.JsonDeserializer;
import com.fasterxml.jackson.databind.ObjectMapper;
import com.fasterxml.jackson.databind.annotation.*;
import com.fasterxml.jackson.annotation.*;


class ProductsEx {

    // Maps the product's availability strings to enum values.
    
	public static Map\<ProductAvailability, String> Availability = new HashMap\<ProductAvailability, String>();
	static {
		Availability.put(ProductAvailability.InStock, "in stock");
		Availability.put(ProductAvailability.OutOfStock, "out of stock");
		Availability.put(ProductAvailability.PreOrder, "preorder");
	}
	
	// Jackson object used to serialize and deserialize JSON.

	private static ObjectMapper jsonMapper = new ObjectMapper();

	private static String accessToken = "<accesstokengoeshere>"; 
    public static String devToken = "<devtokengoeshere>"; 

    // URI templates used to get resources.
    
    public static final String BaseUri = "https://content.api.bingads.microsoft.com/shopping/v9.1";
    public static final String BmcUri = BaseUri + "/bmc/%d";
    public static final String GetUri = BmcUri + "/products/%s";

    // Query strings. 
    
    public static final String queryString = "?alt=json";

    // Replace with your ID.
    
    public static long merchantId = <merchantidgoeshere>; 

    // Replace with the ID of the product to get.

    public static String productId = "Online:EN:US:X_0123";


	// This example gets the specified product offer.
    
	public static void main(String[] args) {

		try {
			Map\<String, String> headers = getCredentialHeaders();

            String url = String.format(GetUri + queryString, merchantId, productId);
            
            // Get the specified product.

            Product product = (Product) getResource(url, headers, Product.class);

    		printProduct(product);
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

    private static Object getResource(String uri, Map\<String, String> headers, Class\<?> type) throws Exception 
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

    // Prints a couple of fields from the Product object.

    private static void printProduct(Product product)
    {
        System.out.println("Product ID: " + product.getId());
        System.out.println("Title: " + product.getTitle());
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

// Converting True/False to Boolean because the serializer can't.

class StringBooleanDeserializer extends JsonDeserializer<Boolean> {
	
	public Boolean deserialize(JsonParser parser, DeserializationContext context) throws IOException, JsonProcessingException {
		return !"False".equals(parser.getText());
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

// Defines a collection of products.

class ProductCollection
{
	private String kind;  // Set to content#productsListResponse
    private String nextPageToken;
    private List<Product> resources;
    
    public String getKind() { return this.kind; }
    public String getNextPageToken() { return this.nextPageToken; }
    public List<Product> getResources() { return this.resources; }
}


// Defines a product resource.

class Product
{
	private List<String> additionalImageLinks;
	
    @JsonProperty("adult")
    @JsonDeserialize(using=StringBooleanDeserializer.class)
	private Boolean isAdult;
    private String adwordsGrouping;
    private List<String> adwordsLabels;
    private String adwordsRedirect;
    private String ageGroup;
    private String availability;
    private String availabilityDate;
    private String brand;
    private String channel;
    private String color;
    private String condition;
    private String contentLanguage;
    private List<ProductCustomAttribute> customAttributes;
    private List<ProductCustomGroup> customGroups;
    private String customLabel0;
    private String customLabel1;
    private String customLabel2;
    private String customLabel3;
    private String customLabel4;
    private String description;
    private List<ProductDestination> destinations;
    private String energyEfficiencyClass;
    private String expirationDate;
    private String gender;
    private String googleProductCategory;
    private String gtin;
    private String id;

    @JsonDeserialize(using=StringBooleanDeserializer.class)
    private Boolean identifierExists;
    private String imageLink;

    @JsonDeserialize(using=StringBooleanDeserializer.class)
    private Boolean isBundle;
    private String itemGroupId;
    private String kind;  //For example: "kind":"content#product"
    private String link;
    private String material;
    
    @JsonProperty("multipack")
    private Long multipackQuantity;
    private String mobileLink;
    private String mpn;
    private String offerId;

    @JsonDeserialize(using=StringBooleanDeserializer.class)
    private Boolean onlineOnly;
    private String pattern;
    private Price price;
    private String productType;
    private Price salePrice;
    private String salePriceEffectiveDate;
    private List<ProductShipping> shipping;
    private ProductShippingWeight shippingWeight;
    private String shippingLabel;
    private List<String> sizes;
    private String sizeSystem;
    private String sizeType;
    private String targetCountry;
    private List<ProductTax> taxes;
    private String title;
    private UnitPricing unitPricingBaseMeasure;
    private UnitPricing unitPricingMeasure;
    private List<String> validatedDestinations;
    
    

	public List<String> getAdditionalImageLinks() { return this.additionalImageLinks; }
	public void setAdditionalImageLinks(List<String> value) { this.additionalImageLinks = value; }

    public Boolean getIsAdult() { return this.isAdult; }
    public void setIsAdult(Boolean value) { this.isAdult = value; }

    public String getAdwordsGrouping() { return this.adwordsGrouping; }
    public void setAdwordsGrouping(String value) { this.adwordsGrouping = value; }

    public List<String> getAdwordsLabels() { return this.adwordsLabels; }
    public void setAdwordsLabels(List<String> value) { this.adwordsLabels = value; }

    public String getAdwordsRedirect() { return this.adwordsRedirect; }
    public void setAdwordsRedirect(String value) { this.adwordsRedirect = value; }

    public String getAgeGroup() { return this.ageGroup; }
    public void setAgeGroup(String value) { this.ageGroup = value; }

    public String getAvailability() { return this.availability; }
    public void setAvailability(String value) { this.availability = value; }

    public String getAvailabilityDate() { return this.availabilityDate; }
    public void setAvailabilityDate(String value) { this.availabilityDate = value; }

    public String getBrand() { return this.brand; }
    public void setBrand(String value) { this.brand = value; }

    public String getChannel() { return this.channel; }
    public void setChannel(String value) { this.channel = value; }

    public String getColor() { return this.color; }
    public void setColor(String value) { this.color = value; }

    public String getCondition() { return this.condition; }
    public void setCondition(String value) { this.condition = value; }

    public String getContentLanguage() { return this.contentLanguage; }
    public void setContentLanguage(String value) { this.contentLanguage = value; }

    public List<ProductCustomAttribute> getCustomAttributes() { return this.customAttributes; }
    public void setCustomAttributes(List<ProductCustomAttribute> value) { this.customAttributes = value; }

    public List<ProductCustomGroup> getCustomGroups() { return this.customGroups; }
    public void setCustomGroups(List<ProductCustomGroup> value) { this.customGroups = value; }

    public String getCustomLabel0() { return this.customLabel0; }
    public void setCustomLabel0(String value) { this.customLabel0 = value; }

    public String getCustomLabel1() { return this.customLabel1; }
    public void setCustomLabel1(String value) { this.customLabel1 = value; }

    public String getCustomLabel2() { return this.customLabel2; }
    public void setCustomLabel2(String value) { this.customLabel2 = value; }

    public String getCustomLabel3() { return this.customLabel3; }
    public void setCustomLabel3(String value) { this.customLabel3 = value; }

    public String getCustomLabel4() { return this.customLabel4; }
    public void setCustomLabel4(String value) { this.customLabel4 = value; }

    public String getDescription() { return this.description; }
    public void setDescription(String value) { this.description = value; }

    public List<ProductDestination> getDestinations() { return this.destinations; }
    public void setDestinations(List<ProductDestination> value) { this.destinations = value; }

    public String getEnergyEfficiencyClass() { return this.energyEfficiencyClass; }
    public void setEnergyEfficiencyClass(String value) { this.energyEfficiencyClass = value; }

    public String getExpirationDate() { return this.expirationDate; }
    public void setExpirationDate(String value) { this.expirationDate = value; }

    public String getGender() { return this.gender; }
    public void setGender(String value) { this.gender = value; }

    public String getGoogleProductCategory() { return this.googleProductCategory; }
    public void setGoogleProductCategory(String value) { this.googleProductCategory = value; }

    public String getGtin() { return this.gtin; }
    public void setGtin(String value) { this.gtin = value; }

    public String getId() { return this.id; }
    public void setId(String value) { this.id = value; }

    public Boolean getIdentifierExists() { return this.identifierExists; }
    public void setIdentifierExists(Boolean value) { this.identifierExists = value; }

    public String getImageLink() { return this.imageLink; }
    public void setImageLink(String value) { this.imageLink = value; }

    public Boolean getIsBundle() { return this.isBundle; }
    public void setIsBundle(Boolean value) { this.isBundle = value; }

    public String getItemGroupId() { return this.itemGroupId; }
    public void setItemGroupId(String value) { this.itemGroupId = value; }

    public String getKind() { return this.kind; } 
    public void setKind(String value) { this.kind = value; } 

    public String getLink() { return this.link; }
    public void setLink(String value) { this.link = value; }

    public String getMaterial() { return this.material; }
    public void setMaterial(String value) { this.material = value; }

    public Long getMultipackQuantity() { return this.multipackQuantity; }
    public void setMultipackQuantity(Long value) { this.multipackQuantity = value; }

    public String getMobileLink() { return this.mobileLink; }
    public void setMobileLink(String value) { this.mobileLink = value; }

    public String getMpn() { return this.mpn; }
    public void setMpn(String value) { this.mpn = value; }

    public String getOfferId() { return this.offerId; }
    public void setOfferId(String value) { this.offerId = value; }

    public Boolean getOnlineOnly() { return this.onlineOnly; }
    public void setOnlineOnly(Boolean value) { this.onlineOnly = value; }

    public String getPattern() { return this.pattern; }
    public void setPattern(String value) { this.pattern = value; }

    public Price getPrice() { return this.price; }
    public void setPrice(Price value) { this.price = value; }

    public String getProductType() { return this.productType; }
    public void setProductType(String value) { this.productType = value; }

    public Price getSalePrice() { return this.salePrice; }
    public void setSalePrice(Price value) { this.salePrice = value; }

    public String getSalePriceEffectiveDate() { return this.salePriceEffectiveDate; }
    public void setSalePriceEffectiveDate(String value) { this.salePriceEffectiveDate = value; }

    public List<ProductShipping> getShipping() { return this.shipping; }
    public void setShipping(List<ProductShipping> value) { this.shipping = value; }

    public ProductShippingWeight getShippingWeight() { return this.shippingWeight; }
    public void setShippingWeight(ProductShippingWeight value) { this.shippingWeight = value; }

    public String getShippingLabel() { return this.shippingLabel; }
    public void setShippingLabel(String value) { this.shippingLabel = value; }

    public List<String> getSizes() { return this.sizes; }
    public void setSizes(List<String> value) { this.sizes = value; }

    public String getSizeSystem() { return this.sizeSystem; }
    public void setSizeSystem(String value) { this.sizeSystem = value; }

    public String getSizeType() { return this.sizeType; }
    public void setSizeType(String value) { this.sizeType = value; }

    public String getTargetCountry() { return this.targetCountry; }
    public void setTargetCountry(String value) { this.targetCountry = value; }

    public List<ProductTax> getTaxes() { return this.taxes; }
    public void setTaxes(List<ProductTax> value) { this.taxes = value; }

    public String getTitle() { return this.title; }
    public void setTitle(String value) { this.title = value; }

    public UnitPricing getUnitPricingBaseMeasure() { return this.unitPricingBaseMeasure; }
    public void setUnitPricingBaseMeasure(UnitPricing value) { this.unitPricingBaseMeasure = value; }

    public UnitPricing getUnitPricingMeasure() { return this.unitPricingMeasure; }
    public void setUnitPricingMeasure(UnitPricing value) { this.unitPricingMeasure = value; }

    public List<String> getValidatedDestinations() { return this.validatedDestinations; }
    public void setValidatedDestinations(List<String> value) { this.validatedDestinations = value; }
}


// Defines a product's price.

class Price
{
	private String currency;
	private Double value;
	
    public String getCurrency() { return this.currency; }
    public void setCurrency(String value) { this.currency = value; }

    public Double getValue() { return this.value; }
    public void setValue(Double value) { this.value = value; }
}


// Defines a product's tax.

class ProductTax
{
	private String country;
	private Long locationId;
	private String postalCode;
	private Double rate;
	private String region;

	@JsonDeserialize(using=StringBooleanDeserializer.class)
	private Boolean taxShip;

    public String getCountry() { return this.country; }
    public void setCountry(String value) { this.country = value; }

    public Long getLocationId() { return this.locationId; }
    public void setLocationId(Long value) { this.locationId = value; }

    public String getPostalCode() { return this.postalCode; }
    public void setPostalCode(String value) { this.postalCode = value; }

    public Double getRate() { return this.rate; }
    public void setRate(Double value) { this.rate = value; }

    public String getRegion() { return this.region; }
    public void setRegion(String value) { this.region = value; }

    public Boolean getTaxShip() { return this.taxShip; }
    public void setTaxShip(Boolean value) { this.taxShip = value; }
}



// Defines a product's shipping weight.

class ProductShippingWeight
{
	private String unit;
	private Double value;
	
    public String getUnit() { return this.unit; }
    public void setUnit(String value) { this.unit = value; }

    public Double getValue() { return this.value; }
    public void setValue(Double value) { this.value = value; }
}


// Defines a product's shipping cost.

class ProductShipping
{
	private String country;
	private String locationGroupName;
	private Long locationId;
	private String postalCode;
	private Price price;
	private String region;
	private String service;
	
    public String getCountry() { return this.country; }
    public void setCountry(String value) { this.country = value; }

    public String getLocationGroupName() { return this.locationGroupName; }
    public void setLocationGroupName(String value) { this.locationGroupName = value; }

    public Long getLocationId() { return this.locationId; }
    public void setLocationId(Long value) { this.locationId = value; }

    public String getPostalCode() { return this.postalCode; }
    public void setPostalCode(String value) { this.postalCode = value; }

    public Price getPrice() { return this.price; }
    public void setPrice(Price value) { this.price = value; }

    public String getRegion() { return this.region; }
    public void setRegion(String value) { this.region = value; }

    public String getService() { return this.service; }
    public void setService(String value) { this.service = value; }
}


// Defines per unit pricing.

class UnitPricing
{
	private String unit;
	private Double value;
	
    public String getUnit() { return this.unit; }
    public void setUnit(String value) { this.unit = value; }

    public Double getValue() { return this.value; }
    public void setValue(Double value) { this.value = value; }
}


// Defines a destination.

class ProductDestination
{
	private String destinationName;
	private String intention;
	
    public String getDestinationName() { return this.destinationName; }
    public void setDestinationName(String value) { this.destinationName = value; }

    public String getIntention() { return this.intention; }
    public void setIntention(String value) { this.intention = value; }
}


// Defines a product's custom attribute.

class ProductCustomAttribute
{
	private String name;
	private String type;
	private String unit;
	private String value;
	
    public String getName() { return this.name; }
    public void setName(String value) { this.name = value; }

    public String getType() { return this.type; }
    public void setType(String value) { this.type = value; }

    public String getUnit() { return this.unit; }
    public void setUnit(String value) { this.unit = value; }

    public String getValue() { return this.value; }
    public void setValue(String value) { this.value = value; }
}


// Defines a custom group of attributes.

class ProductCustomGroup
{
    @JsonProperty("customGroups")
	private List<ProductCustomAttribute> attributes;
    private String name;
	
    public List<ProductCustomAttribute> getAttributes() { return this.attributes; }
    public void setAttributes(List<ProductCustomAttribute> value) { this.attributes = value; }

    public String getName() { return this.name; }
    public void setName(String value) { this.name = value; }
}


// Defines the possible distribution channels.

enum ProductChannel
{
    Online,
    Local
}


//Defines the possible product conditions.

enum ProductCondition
{
	New,
	Refurbished,
	Used
}



//Defines the possible product availability.

enum ProductAvailability
{
	InStock,
	OutOfStock,
	PreOrder
}



// Classes used to handle errors.

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
