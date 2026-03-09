 # Minimal Java HTTP Backend Server (No Frameworks)

A lightweight HTTP backend server built **from scratch in Java** using the built-in `com.sun.net.httpserver` package.
The goal of this project is to understand how backend servers work internally **without using frameworks like Spring Boot**.

---

## Overview

This project demonstrates how to:

* Create a custom HTTP server
* Map routes manually using `createContext`
* Handle requests with `HttpHandler`
* Inspect request details using `HttpExchange`
* Return JSON responses
* Validate HTTP methods
* Read request body data from POST requests

It serves as a **foundation for understanding backend systems and HTTP request handling**.

---

## Endpoints

| Endpoint  | Method | Description                                    |
| --------- | ------ | ---------------------------------------------- |
| `/`       | GET    | Basic welcome endpoint                         |
| `/info`   | GET    | Displays request method, path, and headers     |
| `/json`   | GET    | Returns a JSON response                        |
| `/health` | GET    | Health-check endpoint to confirm server status |
| `/echo`   | POST   | Reads request body and returns it              |

---

## Example Requests

### GET `/json`

Response:

```json
{
  "message": "Hello from Java Backend"
}
```

---

### GET `/health`

Response:

```json
{
  "status": "running"
}
```

---

### POST `/echo`

Request:

```
POST /echo
Body: hello backend
```

Response:

```
hello backend
```

---

## How It Works

The server follows the HTTP lifecycle:

```
Client Request
      ↓
HttpServer
      ↓
Route Mapping (createContext)
      ↓
HttpHandler
      ↓
Response Sent Back
```

Core Java classes used:

* `HttpServer`
* `HttpHandler`
* `HttpExchange`
* `Headers`
* `InputStream`

---

## Running the Project

### Compile

```
javac Server.java
```

### Run

```
java Server
```

The server will start on:

```
http://localhost:8080
```

---

## Testing Endpoints

Open in browser:

```
http://localhost:8080/
http://localhost:8080/json
http://localhost:8080/info
http://localhost:8080/health
```

Test the POST endpoint using curl:

```
curl -X POST http://localhost:8080/echo -d "hello backend"
```

Expected response:

```
hello backend
```

---

## Key Concepts Learned

* HTTP request / response lifecycle
* Backend routing
* Handling request headers
* JSON API responses
* HTTP method validation
* Reading request body streams
* Building backend services without frameworks

---

## Tech Stack

* **Java**
* Built-in `HttpServer`
* No external frameworks

---

## Author

Built as part of my journey learning backend development by implementing core HTTP concepts directly in Java.
