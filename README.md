# SI_Exam_Eureka_Server

## Description
This project is a car rental service which cosists of several microservices with Java Spring Boot with REST and a Eureka server. 
* The Eureka Server makes sure that the other microservices can connect to each other. 
* Car Gateway works as the communicator gateway for the other microservices. This is the the service that the monolithic application contacts to handle all requests. 
* The Car Catalog provides endpoints and sql database for storing and getting available cars for rental. 
* Rent-A-Car service provides a service for saving/deleting car bookings/orders in a mongodb database as well as functionality for getting orders by username or car id. 
* Car Review offer customers a opportunity to make reviews of the cars they have tried, and saves the reviews in MongoDB.
* Translator handles translation to/from json/xml.

Since these are microservices the Car Catalog, Rent-A-Car and Car Review microservices of course have their own individual databases. 

![](https://i.imgur.com/ecvuoxC.png)


## Repos:

[Car Gateway](https://github.com/SOFTBoiS/SI_MP_4_Car_Gateway)  
[Car Catalog](https://github.com/SOFTBoiS/SI_MP_4_Car_Catalog)  
[Rent-A-Car](https://github.com/SOFTBoiS/SI_Exam_Rent_A_Car)  
[Translator](https://github.com/SOFTBoiS/SI_Exam_translator)  
Optional: [Review Catalog](https://github.com/SOFTBoiS/SI_MP_4_Review_Catalog)  

## How to
1. Replace the mongodb connection string in the Rent-A-Car [application.properties](https://github.com/SOFTBoiS/SI_Exam_Rent_A_Car/blob/main/src/main/resources/application.properties) with your own.  
Do the same with Review Catalog if you use it. 
2. Run Eureka server.
3. Run Car Catalog.
4. Run Rent-A-Car.
5. Run Car Gateway.
6. (Run Review Catalog)

## Gateway endpoints

| Description              | URL                                        | Method | Body                                            |
| :----------------------- | :----------------------------------------- | :----- | :---------------------------------------------- |
| Get cars      | http://localhost:8081/mycars/| GET    |                                       |
| Create car order| http://localhost:8081/orders/| POST | See "xml block 1" or "json block 1"                    |
| Delete car order| http://localhost:8081/orders/{order mongoid} or the href for the order| DELETE|                                                                           |
| Get orders by username | http://localhost:8081/orders/username/{username} | GET|              |
| Get orders by car id| http://localhost:8081/orders/car-id/{carId}| GET|                       |


xml block 1:
```xml
<order>
  <username>Sebastian</username>
  <carId>100</carId>
  <startDate>2020-01-24</startDate>
  <endDate>2020-03-24</endDate>
  <price>200000</price>
</order>
```

json block 1 : 
```json
{
    "username": "Sebastian",
    "carId": 100,
    "startDate": "2020-01-24",
    "endDate": "2020-03-24",
    "price": 200000
}
```
