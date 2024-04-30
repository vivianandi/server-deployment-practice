# Server Deployment Practice
This project is an example of a basic server setup using Node.js and Express. It includes routes, middleware, and error handling to demonstrate a simple API structure.

## Getting Started
### Prerequisites
- Node.js
- npm

### Installing
1. First, clone the repository to your local machine
2. Then, navigate to the project directory and install the required packages: `npm install`

### Running the Server
To start the server, run: `npm index.js`

This will start the server on the port specified in your environment variables (.env file)

## Functionality
### Routes
`GET /`: Returns a simple "Hello World" message

`GET /data`: Returns a JSON object with numeric keys showing "odd" or "even" and includes a timestamp added by middleware

`GET /bad`: Simulates a server error to demonstrate error handling

### Middleware
**Timestamp Middleware:** Appends a timestamp to the request object on routes that include it

### Error Handling
**404 Not Found:** Any undefined routes will trigger a 404 error with a detailed message

**500 Server Error:** Simulates an internal server error for demonstration purposes with detailed diagnostics

## Testing
The tests are written using Jest and Supertest. They check the functionality of all routes, including error handling and the timestamp middleware.

To run the tests, execute: `npm test`

### Test Cases
- 404 for invalid URL: Checks if navigating to an undefined route returns a 404 status

- 500 for simulated server error: Checks if the /bad route returns a 500 status

- Root path returns Hello World: Ensures the root path correctly returns a 200 status and the text "Hello World"

- Data path checks: Verifies that the /data path returns a 200 status and the response is an object with a time field stamped by middleware
