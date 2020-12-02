# SI_MP_4_Eureka_Server

## Repos:

[Car Gateway](https://github.com/SOFTBoiS/SI_MP_4_Car_Gateway)  
[Car Catalog](https://github.com/SOFTBoiS/SI_MP_4_Car_Catalog)  
[Review Catalog](https://github.com/SOFTBoiS/SI_MP_4_Review_Catalog)

## How to
1. Replace the mongodb connection string in the Review Catalog [application.properties](https://github.com/SOFTBoiS/SI_MP_4_Review_Catalog/blob/main/src/main/resources/application.properties) with your own.  
2. Run the Eureka server.
3. Run the Car Catalog.
4. Run the Review Catalog.
5. Run the Car Gateway.

**Before making any review requests, you should create some users with some cars**

## Gateway endpoints

| Description              | URL                                        | Method | Body                                            |
| :----------------------- | :----------------------------------------- | :----- | :---------------------------------------------- |
| Post a review            | localhost:8080/reviews                     | POST   | { "username": "adma", "carId": 2, "rating": 5 } |
| Get Reviews from a user  | localhost:8080/reviews/username/{username} | GET    |
| Get reviews from a carId | localhost:8080/reviews/car-id/{carId}      | GET    |

## Important Review endpoints

| Description   | URL                   | Method | Body                                  |
| :------------ | :-------------------- | :----- | :------------------------------------ |
| Create a user | localhost:8091/users/ | POST   | {"username": "adma", "cars": [1, 2] } |
