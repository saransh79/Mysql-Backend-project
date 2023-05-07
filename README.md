# Nodejs Express API Tutorial: Sequelize and JWT

In this project, there are API that will manage the below listed services and that supports Token Based Authentication with JWT ( JSON Web Token ).
- **Token Authentication Services**
  - Signup
  - Signin for token and to below property services.
- **Property Services**  
  - Create list of Properties
  - Update Property Details By Id
  - Read Property By Id
  - Read Property Details
  - Delete Property by Id
  - Delete All Properties

Signin process will be providing token and the same token will be used to execute all of properties services **( ex: create, update, read, delete )**. Token need to pass through a request header to call property services, this security layer to implement a secure API.

**The Client typically attaches JWT in Authorization header with Bearer prefix:**
    
        Authorization: Bearer [header].[payload].[signature]

**Or only in x-access-token header:**

        x-access-token: [header].[payload].[signature]


**This application will list the following about each Property:**

- Property Name
- Address
- City
- Country
- Property Type
- Minimum Price
- Maximum Price
- Ready to Sell or not?

## What We will Achieve?

 - Appropriate Flow for User Signup & User Login with JWT Authentication
 - Node.js Express Architecture with CORS, Authentication & Authorization middlewares & Sequelize
 - Apply JWT Authentication for Properties CURD services
 - How to configure Express routes to work with JWT
 - How to define Data Models and association for Authentication and Authorization
 - Way to use Sequelize to interact with MySQL Database
 
 API's Used-

**POST** /api/auth/signup - Signup new account

**POST** /api/auth/signin - Login an account

**POST** /api/properties - Create New Property

**GET** /api/properties - Get All Properties

**GET** /api/properties/58 - Get Single Property with id=58

**PUT** /api/properties/58 - Update Single Property With id=58

**DELETE** /api/properties/58 - Remove Single Property with id=58

**DELETE** /api/properties - Remove All Properties

## Technology Stack
- Express 4.17.1
- bcryptjs 2.4.3
- jsonwebtoken 8.5.1
- Sequelize 5.21.3
- MySQL

## Project Structure

This is directory structure for our Node.js Express application:

![Node.js Express REST API](https://github.com/TravelXML/REST-API-WITH-PYTHON-PHP-NODEJS-GO-DJANGO-LARAVEL-LUMEN-Examples/blob/main/images/Nodejs-Jwt-1.png)

– config

    - configure MySQL database & Sequelize
    - configure Auth Key

– routes

    - auth.routes.js: POST signup & signin
    - user.routes.js: GET public & protected resources
    - property.routes.js: GET, POST & protected resources

– middlewares

    - verifySignUp.js: check duplicate Username or Email
    - authJwt.js: verify Token, check User roles in database

– controllers

    - auth.controller.js: handle signup & signin actions
    - user.controller.js: return public & protected content
    - property.controller.js: return properties content

– models for Sequelize Models

    - user.model.js
    - role.model.js
    - property.model.js

– server.js: import and initialize necessary modules and routes, listen for connections.
