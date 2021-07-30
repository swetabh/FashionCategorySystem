This project is a simple Java Based application applying some Business conditions which as per the following logic:

- User can create fashion category data in tree hierarchy.
- User can update the existing category
- User can delete the existing category
- User can view the list of already addded categories

### Note-> I have added the "DB_Script.sql" in the sql folder and the postman collection in resources folder (FashionCategorySystem.postman_collection.json) which can be used for reference. Swagger can also be used for running the apis.

Assumptions :
- MS SQL Server database will be used for the application. 
- DB script will be run before running the apis on the database. Environment specific configuration can be done in application.yml file
- The structure of the fashion category is fixed. Only the data can be changed.
- The category structure is at max predefined sub level of 4


### API Details:

- 1.> The category listing api

	URL :http://localhost:8080/api/fashion/category/list
	METHOD : GET

- 2.> The Create api

	URL : http://localhost:8080/api/fashion/category/create
	METHOD : POST
	HEADERS: Content-Type : application/json
	Payload(Sample JSON) : 
	{
	  "name": "Women",
	  "description": "Women",
	  "fashionCategoryList": [
	    {
	      "name": "Clothing",
	      "description": "Clothing",
	      "fashionCategoryTypes": [
	        {
	          "name": "Dress",
	          "description": "Dress",
	          "fashionCategorySubTypes": [
	            {
	              "name": "Causal Dresses",
	              "description": "Causal Dresses"
	            }
	          ]
	        }
	      ]
	    }
	  ]
	}

- 3.> The Update api by 

	URL : http://localhost:8080/api/fashion/category/update
	METHOD : POST
	HEADERS: Content-Type : application/json
	Payload(Sample JSON) : 
	{
	  "name": "Women",
	  "description": "Women",
	  "fashionCategoryList": [
	    {
	      "name": "Clothing",
	      "description": "Clothing",
	      "fashionCategoryTypes": [
	        {
	          "name": "Dress",
	          "description": "Dress",
	          "fashionCategorySubTypes": [
	            {
	              "name": "Causal Dresses",
	              "description": "Causal Dresses"
	            }
	          ]
	        }
	      ]
	    }
	  ]
	}
- 4.> The Delete by ID api

	URL :http://localhost:8080/api/fashion/category/deletebyid/{categoryId}
	METHOD : DELETE
	PARAMS : Category ID
- 5.> The Delete by Category Name api

	URL :http://localhost:8080/api/fashion/category/deletebyname/{categoryName}
	METHOD : DELETE
	PARAMS : Category Name

##### Note: In order to run the project, kindly download the source code and run the FashionCategoryApplication class

## Swagger Configuration

swagger api end point can be accessed via 
- http://localhost:8080/swagger-ui/index.html
 
## Requirements

For building and running the application you need:

- [JDK 1.8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
- [Maven 3](https://maven.apache.org)

## Approach Discussion

It's a stand alone application consist of all Possible test cases. Following are the approach has been taken to address this assignment

1. Designed in a way that all the use cases can be tested independently.

## How to Run

	Run the FashionCategoryApplication class and call the rest apis mentioned above

## How to get Coverage
```shell
mvn clean install
```
it will generate coverage reports in FashionCategorySystem\target\site\jacoco
Open index.html
