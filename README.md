# K Group Developer Trainee assignment: back-end for product rating micro service

This project is part of a home assignment for K Group's Developer Trainee program application. It is the API gateway for the 3 micro service clients:

- Product catalog service
- Product info service
- Ratings data service:

The back-end logic for both the server and the clients is explained in this document.

## What does it do?

This micro service lists user's rated products. In the client, the user may view their own rated products (tab "Home") and also all products (tab "Products").

## How does it work?

The back-end logic is as follows:

- Discovery Server (API gateway) serves the 3 micro services/clients and enables that they can retrieve data from each other.
- Product catalog service offers an API ("catalog/{userId}") that shows user's products that they have rated. It fetches the product data from the Product info service and rating data from Ratings Data service
- Product info service offers an API ("/api/products") that shows a list of all products. It utilizes Spring Data REST API.
- Ratings data service offers two API's: one that shows a product and its rating ("/ratingsdata/products/{productId}") and one that shows user's ratings and their comments for products ("/ratingsdata/users/{userId}")

The back-end repositories for the micro service are found as follows:

- Discovery server: [https://github.com/ullataponen/discovery-server](https://github.com/ullataponen/discovery-server)
- Product catalog service: [https://github.com/ullataponen/product-catalog-service](https://github.com/ullataponen/product-catalog-service)
- Product info service: [https://github.com/ullataponen/product-info-service](https://github.com/ullataponen/product-info-service)
- Ratings data service: [https://github.com/ullataponen/ratings-data-service](https://github.com/ullataponen/ratings-data-service)

In order to run the project, all 4 back-end services must be copied to local environment and their Spring Boot Application files (located in each repository)be run in a code editor/IDE. This file is located in the following directory in each repository: `{project-name}\src\main\java\fi\taponen\{projectnamewithoutdash}`.

Front-end repository is available at [https://github.com/ullataponen/product-rating-client](https://github.com/ullataponen/product-rating-client). Its README includes the instructions on how to run it.

## Who will use this project?

The project is a home assignment for K Group's Developer Trainee 2021 program application and it may be used by K Group for evaluation purposes. The creator and repository owner may use the skills learned during this project in future projects.

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