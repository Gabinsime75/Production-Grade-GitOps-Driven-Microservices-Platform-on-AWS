# Production-Grade-GitOps-Driven-Microservices-Platform-on-AWS

# 🏗️ Architecture
## Applications Architecture
Online Boutique is a polyglot, microservices-based application consisting of 11 independently deployable services that communicate through well-defined gRPC
![alt text](https://github.com/Gabinsime75/Production-Grade-GitOps-Driven-Microservices-Platform-on-AWS/blob/main/Docs/Architecture/Applications-Architecture.png)

| Service                                                                                                                                          | Language      | Description                                                                                                                                                  |
| ------------------------------------------------------------------------------------------------------------------------------------------------ | ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [frontend](https://github.com/laxmikantagiri/Production-Grade_GitOps-Driven_Microservices-Demo/blob/main/src/frontend)                           | Go            | Exposes the application’s HTTP interface, serves the website, and automatically generates session IDs without requiring user registration or authentication. |
| [cartservice](https://github.com/laxmikantagiri/Production-Grade_GitOps-Driven_Microservices-Demo/blob/main/src/cartservice)                     | C#            | Manages shopping-cart operations and persists each user’s cart data in Redis.                                                                                |
| [productcatalogservice](https://github.com/laxmikantagiri/Production-Grade_GitOps-Driven_Microservices-Demo/blob/main/src/productcatalogservice) | Go            | Provides product catalog data from a JSON file and supports product listing, search, and individual product retrieval.                                       |
| [currencyservice](https://github.com/laxmikantagiri/Production-Grade_GitOps-Driven_Microservices-Demo/blob/main/src/currencyservice)             | Node.js       | Converts monetary amounts between currencies using exchange rates obtained from the European Central Bank. It is the application’s highest-QPS service.      |
| [paymentservice](https://github.com/laxmikantagiri/Production-Grade_GitOps-Driven_Microservices-Demo/blob/main/src/paymentservice)               | Node.js       | Simulates credit-card payment processing and returns a transaction ID for successfully processed charges.                                                    |
| [shippingservice](https://github.com/laxmikantagiri/Production-Grade_GitOps-Driven_Microservices-Demo/blob/main/src/shippingservice)             | Go            | Calculates shipping-cost estimates from cart contents and simulates shipment to the customer’s address.                                                      |
| [emailservice](https://github.com/laxmikantagiri/Production-Grade_GitOps-Driven_Microservices-Demo/blob/main/src/emailservice)                   | Python        | Simulates sending an order-confirmation email to the customer after checkout.                                                                                |
| [checkoutservice](https://github.com/laxmikantagiri/Production-Grade_GitOps-Driven_Microservices-Demo/blob/main/src/checkoutservice)             | Go            | Orchestrates the checkout workflow by retrieving the cart, preparing the order, processing payment, arranging shipping, and triggering email confirmation.   |
| [recommendationservice](https://github.com/laxmikantagiri/Production-Grade_GitOps-Driven_Microservices-Demo/blob/main/src/recommendationservice) | Python        | Generates product recommendations based on products currently associated with the user’s shopping activity.                                                  |
| [adservice](https://github.com/laxmikantagiri/Production-Grade_GitOps-Driven_Microservices-Demo/blob/main/src/adservice)                         | Java          | Returns contextual text advertisements based on the keywords provided in the request.                                                                        |
| [loadgenerator](https://github.com/laxmikantagiri/Production-Grade_GitOps-Driven_Microservices-Demo/blob/main/src/loadgenerator)                 | Python/Locust | Continuously generates realistic shopping traffic against the frontend to validate application behavior and performance under load.                          |


## Project Architecture
![alt text](https://github.com/Gabinsime75/Production-Grade-GitOps-Driven-Microservices-Platform-on-AWS/blob/main/Docs/Architecture/Project-Arcgitecture.png)

