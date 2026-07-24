# HTTP Fundamentals 

## 1. What is HTTP?

**HTTP (HyperText Transfer Protocol)** is the protocol used to send data between a client and a server.

It can send:

* Web pages
* Images
* Videos
* JSON
* Files

Example:

```
Browser → HTTP Request → Server
Browser ← HTTP Response ← Server
```

---

## 2. Client and Server

### Client

The client sends a request.

Examples:

* Web browser
* Mobile app
* Java application

---

### Server

The server receives the request.

It:

* Processes the request.
* Gets data.
* Sends a response.

Examples:

* Apache
* Nginx
* Spring Boot Application

---

## 3. HTTP Request

An HTTP request has four parts.

### URL

The address of the resource.

Example:

```
https://example.com/students
```

---

### Method

The action.

Examples:

* GET
* POST
* PUT
* PATCH
* DELETE

---

### Headers

Extra information.

Example:

```
Content-Type: application/json
```

---

### Body

The data sent to the server.

Usually used with:

* POST
* PUT
* PATCH

GET usually has no body.

---

## 4. HTTP Response

The server sends back:

* Status Code
* Headers
* Body

Example:

```json
{
  "id": 1,
  "name": "Ali"
}
```

---

## 5. HTTP Methods

### GET

Read data.

Example:

```
GET /students
```

---

### POST

Create new data.

Example:

```
POST /students
```

---

### PUT

Replace all data.

Example:

```
PUT /students/5
```

---

### PATCH

Update only part of the data.

Example:

```
PATCH /students/5
```

---

### DELETE

Delete data.

Example:

```
DELETE /students/5
```

---

## 6. Status Codes

### 200 OK

The request worked.

---

### 201 Created

A new resource was created.

Usually after POST.

---

### 204 No Content

Success.

Nothing is returned.

---

### 302 Found

Redirect to another page.

---

### 404 Not Found

The requested resource does not exist.

---

### 500 Internal Server Error

The server has a problem.

---

## 7. Headers

Headers contain extra information.

Examples:

```
Content-Type: application/json
```

```
Authorization: Bearer <token>
```

```
Accept: application/json
```

---

## 8. HTTP Versions

### HTTP/1.0

* One TCP connection for each request.
* Slow.

---

### HTTP/1.1

Better than 1.0.

New features:

* Keep-Alive
* Reuse one connection
* Faster

---

### HTTP/2

Even faster.

New features:

* Multiplexing (many requests on one connection)
* Header compression
* Binary protocol
* Server Push

---

### HTTP/3

Newest version.

Uses:

**QUIC over UDP**

Benefits:

* Faster connection.
* Better performance on unstable networks.
* Lower delay.

---

## 9. TCP and UDP

### TCP

* Reliable.
* Checks that all data arrives.
* Used by HTTP/1.0, HTTP/1.1, and HTTP/2.

---

### UDP

* Faster.
* Less overhead.
* Used by HTTP/3 through QUIC.

---

## 10. HTTPS

HTTPS is the secure version of HTTP.

It encrypts the data.

Uses:

**TLS (Transport Layer Security)**

This protects:

* Passwords
* Credit card numbers
* Personal information

---

## 11. OSI Model

HTTP works at the **Application Layer (Layer 7).**

Below it:

* Layer 4 → TCP / UDP
* Layer 3 → IP
* Layer 2 → MAC
* Layer 1 → Physical network

You do not need to know every detail now, but remember:

> HTTP needs TCP or UDP to send data over the network.

---

## 12. Web Servers

A web server receives HTTP requests.

Examples:

* Apache
* Nginx
* IIS
* Spring Boot (embedded Tomcat)
* Node.js

---

## 13. HTTP Clients

Many programs can send HTTP requests.

Examples:

* Browser
* Java HttpClient
* JavaScript Fetch API
* Postman
* curl

---

## 14. Browser Developer Tools

Modern browsers have **Developer Tools**.

The **Network** tab lets you see:

* Request URL
* Method
* Headers
* Response
* Status Code
* Time

Backend developers use this tool every day.

---

# Key Points to Remember

* HTTP is used for communication between clients and servers.
* A request has **URL, Method, Headers, and Body**.
* A response has **Status Code, Headers, and Body**.
* GET reads data.
* POST creates data.
* PUT replaces data.
* PATCH updates part of the data.
* DELETE removes data.
* HTTP/1.1 is faster than HTTP/1.0 because it reuses connections.
* HTTP/2 adds multiplexing and better performance.
* HTTP/3 uses QUIC over UDP for faster communication.
* HTTPS uses TLS to encrypt data.
* HTTP works on **OSI Layer 7**.
* Spring Boot applications communicate with clients using HTTP.

---