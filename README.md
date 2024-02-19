# E-commerce Pricing Data Retrieval Service

## Description
This project aims to create a Java Spring Boot application following the hexagonal architecture. It provides a REST endpoint for retrieving pricing data from an e-commerce company's database. The application accepts input parameters such as application date, product identifier, and chain identifier, and returns the corresponding pricing information including product identifier, chain identifier, applicable price list, application dates, and final price to be applied.

## Architecture
The application follows the hexagonal architecture, also known as the ports and adapters architecture. This architecture emphasizes a clear separation of concerns and a modular design. Dependencies flow inward from the edges toward the core of the application, allowing for easy component substitution and improved testability.

### Structure
-   **Domain:** Contains the business logic of the application, including models and repositories.
-   **Application:** Contains use cases or application services that encapsulate the business logic. These services are used to interact with the domain.
-   **Infrastructure:** Contains concrete implementations of the ports defined in the domain, as well as adapters to interact with external elements such as databases or REST services.

## Table Structure
The application relies on the following table structure:

#### PRICES Table
-   **BRAND_ID:** Foreign key representing the chain group (1 = MAIN_GROUP).
-   **START_DATE, END_DATE:** Date range during which the specified price list is applicable.
-   **PRICE_LIST:** Identifier of the applicable price list.
-   **PRODUCT_ID:** Product identifier code.
-   **PRIORITY:** Price application disambiguator. If two price lists coincide within a date range, the one with the highest priority (highest numeric value) is applied.
-   **PRICE:** Final selling price.
-   **CURR:** ISO currency code.

## How to Use
1.   Ensure you have Java (version 17) and Maven installed on your system.
2.   Clone this repository to your local machine.
3.   Navigate to the project directory.
4.   Build the project using Maven: ```mvn clean install```.
5.   Run the application: java -jar target/ecommerce-pricing-service.jar.
6.   Make HTTP requests to the provided REST endpoint with the required parameters (date, productId, brandId) to retrieve pricing information.

## Dependencies
-   Java 17
-   Maven
-   Spring Boot 3.2.2
-   Spring Data JPA
-   Spring Web
-   H2 Database

## Contributors
***Alejandro Velázquez López***

## License
This project is licensed under the MIT License.
