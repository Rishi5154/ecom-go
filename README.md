**README**
===============

**Project Name**
---------------

Ecommerce API

**Description**
---------------

This is a very simple ecommerce API built using Go, providing endpoints for user authentication, product management, cart management, and order management.

**API Endpoints**
----------------

### User Endpoints

* **POST /login**: Login a user
	+ Request Body: `{"email": "string", "password": "string"}`
	+ Response: `{"token": "string"}`
* **POST /register**: Register a new user
	+ Request Body: `{"email": "string", "password": "string", "firstName": "string", "lastName": "string"}`
	+ Response: `{"id": "int", "email": "string", "name": "string"}`

### Product Endpoints

* **POST /products**: Create a new product
	+ Request Body: `{"name": "string", "price": "float", "description": "string"}`
	+ Response: `{"id": "int", "name": "string", "price": "float", "description": "string"}`
* **GET /products**: Get all products
	+ Response: `[{"id": "int", "name": "string", "price": "float", "description": "string"}]`

### Cart Endpoints

* **POST /cart/checkout**: Checkout cart
	+ Request Body: `{"products": [{"id": "int", "quantity": "int"}]}`
	+ Response: `{"order_id": "int", "total_price": "float"}`


**API Specs**
-------------

The API uses JSON Web Tokens (JWT) for authentication. The `Authorization` header should be included in all requests with the token obtained from the login endpoint.

The API uses the following HTTP status codes:

* 200 OK: Successful request
* 401 Unauthorized: Invalid or missing token
* 404 Not Found: Resource not found
* 500 Internal Server Error: Server error

**Technologies Used**
--------------------

* Go
* Gorilla Mux
* MySQL
* JWT