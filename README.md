Short-Term Stay API Gateway

This repository contains the API Gateway for the short-term stay platform, built using .NET and the Ocelot plugin.
The gateway acts as a centralized entry point for managing all interactions with the backend services, providing secure and seamless routing between clients and the underlying APIs.

Overview
The API Gateway simplifies communication between the frontend and backend microservices by handling:

    Routing: Maps upstream requests (from clients) to downstream services.
    Authentication: Secures sensitive endpoints using JWT-based authentication.

The gateway has been thoroughly tested using Postman, ensuring all routes work as expected.
Gateway Configuration

The gateway uses Ocelot's configuration to define routing rules between upstream and downstream endpoints. Below is an explanation of the key routes and their functionalities.
(See ocelot.json file).
    
Endpoints:
### Endpoints  

| **Upstream Endpoint**      | **HTTP Method** | **Downstream Endpoint**                              
|----------------------------|-----------------|-----------------------------------------------------| 
| `/auth/login`              | POST            | `/api/v1.0/Authentication/Login`                   |  
| `/listing/insert`          | POST            | `/api/v1.0/Listing/InsertListing`                  |   
| `/listing/query`           | GET             | `/api/v1.0/Listing/QueryListingWithPaging`         |  
| `/listing/report`          | GET             | `/api/v1.0/Listing/ReportListingsWithPaging`       |   
| `/stay/book`               | POST            | `/api/v1.0/Stay/BookStay`                          |   
| `/stay/mystays`            | GET             | `/api/v1.0/Stay/ShowMyStays`                       |   
| `/review/stay`             | POST            | `/api/v1.0/Review/ReviewStay`                      |   


Base URL:
The API Gateway is hosted at:
https://localhost:7083 

Routing:

    UpstreamPathTemplate: Defines the API Gateway endpoint accessible to clients.
    DownstreamPathTemplate: Defines the actual backend service endpoint being called.
    DownstreamHostAndPorts: Specifies the backend host and port for routing traffic.

Testing
To test the API Gateway:

    I used Postman to send requests to the Upstream Endpoints listed above.
    For secured routes, include the following header with a valid JWT token:
  Authorization: Bearer "your-jwt-token"  

Video link -> [https://youtu.be/XZuYFbYHEEM](https://youtu.be/XZuYFbYHEEM)
