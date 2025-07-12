# Bookstore RESTful API
A comprehensive RESTful API for a bookstore application implemented using JAX-RS. This project was developed as part of a coursework assignment.

## Project Overview
This API provides endpoints for managing books, authors, customers, shopping carts, and orders in an online bookstore system. It follows REST architectural principles and uses in-memory data structures for storage.

## Technologies Used
- JAX-RS for creating RESTful web services
- Jersey as the JAX-RS implementation
- Jackson for JSON processing
- Apache Tomcat server for deployment
- JSON as the data format for request and response bodies
- In-memory data storage (HashMaps, ArrayLists)
- Maven for dependency management and build
- Java 8

## Key Features
- **Books Management**: Create, retrieve, update, and delete books
- **Authors Management**: Manage author information and retrieve books by author
- **Customers Management**: Handle customer accounts and preferences
- **Shopping Cart**: Add, update, and remove items from customer carts
- **Order Processing**: Create orders from carts and view order history

## API Endpoints
### Book Resource (/books)
- `POST /books`: Create a new book
- `GET /books`: Get all books
- `GET /books/{id}`: Get a specific book by ID
- `PUT /books/{id}`: Update a book
- `DELETE /books/{id}`: Delete a book

### Author Resource (/authors)
- `POST /authors`: Create a new author
- `GET /authors`: Get all authors
- `GET /authors/{id}`: Get a specific author by ID
- `PUT /authors/{id}`: Update an author
- `DELETE /authors/{id}`: Delete an author
- `GET /authors/{id}/books`: Get all books by an author

### Customer Resource (/customers)
- `POST /customers`: Create a new customer
- `GET /customers`: Get all customers
- `GET /customers/{id}`: Get a specific customer by ID
- `PUT /customers/{id}`: Update a customer
- `DELETE /customers/{id}`: Delete a customer

### Cart Resource (/customers/{customerId}/cart)
- `GET /customers/{customerId}/cart`: Get a customer's cart
- `POST /customers/{customerId}/cart/items`: Add an item to a cart
- `PUT /customers/{customerId}/cart/items/{bookId}`: Update an item in a cart
- `DELETE /customers/{customerId}/cart/items/{bookId}`: Remove an item from a cart

### Order Resource (/customers/{customerId}/orders)
- `POST /customers/{customerId}/orders`: Create an order from a customer's cart
- `GET /customers/{customerId}/orders`: Get all orders for a customer
- `GET /customers/{customerId}/orders/{orderId}`: Get a specific order

## Exception Handling
The API includes custom exception handling for:
- BookNotFoundException
- AuthorNotFoundException
- CustomerNotFoundException
- InvalidInputException
- OutOfStockException
- CartNotFoundException

## Setup and Running

### Prerequisites
- Java 8 or higher
- Maven 3.6+
- Apache Tomcat 9.0+

### Installation Steps
1. Clone this repository
2. Build the project using Maven: `mvn clean package`
3. Deploy the generated WAR file to Apache Tomcat:
   - Copy `target/CSABookStoreAPI-1.0-SNAPSHOT.war` to your Tomcat `webapps` directory
   - Start Tomcat server
4. The API will be available at: `http://localhost:8080/CSABookStoreAPI-1.0-SNAPSHOT/api/`

### Alternative Setup (Development)
For development purposes, you can also run the application using Maven with an embedded server, but deployment to Apache Tomcat is the recommended approach for this coursework.

## Testing
The API can be tested using Postman. Example requests for each endpoint are provided in the project documentation.

## Author
- Yasith

## License
This project is submitted as coursework and is subject to academic guidelines.
