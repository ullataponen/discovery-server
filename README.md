# Back-end for product rating micro service

This project is part of a micro service that provides user's product rating information. It is the discovery server/API gateway for the 3 micro service clients:

- Product catalog service
- Product info service
- Ratings data service:

The back-end logic for both the server and the clients is explained in this document.

## What does it do?

This micro service lists user's rated products. In the client, the user may view their own rated products (tab "Home") and also all products (tab "Products").

## How does it work?

The back-end logic is as follows:

### Discovery Server:

(API gateway) serves the 3 micro services/clients and enables that they can retrieve data from each other.

### Product Catalog Service:

offers an API ("catalog/{userId}") that shows user's products that they have rated. In development phase the data is shown with any user id, e.g. "catalog/foo". It fetches the product data from the Product info service and rating data from Ratings Data service.

![An API result for Product Catalog Service](https://github.com/ullataponen/discovery-server/blob/master/images/product-catalog-service.PNG?raw=true)

### Product Info Service:

offers an API ("/api/products") that shows a list of all products. It utilizes Spring Data REST API.

![An API result for Product Info Service](https://github.com/ullataponen/discovery-server/blob/master/images/product-info-service.PNG)

### Ratings data service:

offers two API's:

- ("/ratingsdata/products/{productId}") shows a product and its rating

![An API result for Ratings Data Service, user data](https://github.com/ullataponen/discovery-server/blob/master/images/ratings-data-service-user.PNG)

- ("/ratingsdata/users/{userId}") shows user's ratings and their comments for products

![An API result for Ratings Data Service, product data](https://github.com/ullataponen/discovery-server/blob/master/images/ratings-data-service-product.PNG)

The back-end repositories for the micro service are found as follows:

- Discovery server: [https://github.com/ullataponen/discovery-server](https://github.com/ullataponen/discovery-server)
- Product catalog service: [https://github.com/ullataponen/product-catalog-service](https://github.com/ullataponen/product-catalog-service)
- Product info service: [https://github.com/ullataponen/product-info-service](https://github.com/ullataponen/product-info-service)
- Ratings data service: [https://github.com/ullataponen/ratings-data-service](https://github.com/ullataponen/ratings-data-service)

In order to run the project, all 4 back-end services must be copied to local environment and their Spring Boot Application files (located in each repository)be run in a code editor/IDE. This file is located in the following directory in each repository: `{project-name}\src\main\java\fi\taponen\{projectnamewithoutdash}`.

Front-end repository is available at [https://github.com/ullataponen/product-rating-client](https://github.com/ullataponen/product-rating-client). Its README includes the instructions on how to run it.

## Who will use this project?

Anyone can copy the repository for their own, non-commercial purposes. The creator and repository owner may use the skills learned during this project in future projects.

## What is the goal of this project?

This project's purpose is to show the skill level of the creator and the ability to create a micro service.

## Used technologies (back-end only)

- Java & Spring Boot
- Spring JPA
- Spring Data REST
- Spring Cloud
- Eureka Server
- Eureka Client
- Hystrix
