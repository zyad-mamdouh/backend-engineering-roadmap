## 1. What is an API?

An **API (Application Programming Interface)** lets two programs talk to each other.

Example:

- Mobile App → API → Server → Database

The app sends a request.

The server sends a response.

---

## 2. Why Do We Use APIs?

### Connect different systems

Example:

A travel app uses the **Google Maps API** to get directions.

---

### Connect Frontend and Backend

The frontend sends requests.

The backend:

- Receives the request.
- Works with the database.
- Sends data back.

---

## 3. Types of APIs

| API Type | Used For |
| --- | --- |
| REST | Most web applications |
| SOAP | Old enterprise systems |
| GraphQL | Client chooses the data it wants |
| gRPC | Fast communication between services |
| WebSockets | Real-time apps like chat |

The most common today is **REST API**.

---

## 4. REST API

REST uses:

- HTTP
- JSON

A client sends an HTTP request.

The server returns an HTTP response.

---

## 5. JSON

JSON is a simple way to send data.

Example:

```json
{
  "id": 1,
  "name": "Ali",
  "age": 20 
}
```

JSON supports:

- String
- Number
- Boolean
- Array
- Object
- Null

---

## 6. HTTP Methods

### GET

Read data.

Example:

Get all students.

---

### POST

Create new data.

Example:

Add a new student.

---

### PUT

Replace all data.

Example:

Replace the whole student record.

---

### PATCH

Update only part of the data.

Example:

Change only the student's email.

---

### DELETE

Delete data.

Example:

Delete a student.

---

## 7. Idempotency

An operation is **idempotent** if repeating it gives the same final result.

### Idempotent

- PUT
- DELETE

Example:

Delete the same student 10 times.

The final result is still:

Student does not exist.

---

### Not Idempotent

POST

If you send POST many times,

you may create many new records.

---

## 8. Endpoint

An **Endpoint** is the URL used with an HTTP method.

Example:

```
GET /students
```

or

```
POST /students
```

---

## 9. Path Parameters

Used to identify one resource.

Example:

```
GET /students/15
```

15 is the student ID.

---

## 10. Query Parameters

Used for filtering or sorting.

Example:

```
GET /students?age=20
```

or

```
GET /students?sort=name
```

---

## 11. Request Body

The **Body** contains data sent to the server.

Example:

```json
{
  "name": "Ali",
  "email": "ali@test.com"
}
```

Passwords and important data should be sent in the **Body**, not in the URL.

---

## 12. Response

The server sends back:

- Status Code
- Data

Example:

```json
{
  "id": 1,
  "name": "Ali"
}
```

---

## 13. Status Codes

### 200

Success.

---

### 201

Created successfully.

Usually after POST.

---

### 400

Client error.

The request is wrong.

---

### 500

Server error.

Something failed on the server.

---

## 14. Headers

Headers give extra information.

Example:

```
Content-Type: application/json
```

This tells the server the body contains JSON.

---

# Key Points to Remember

- An API lets applications communicate.
- REST is the most common API style.
- REST uses HTTP and JSON.
- JSON is used to send data.
- GET reads data.
- POST creates data.
- PUT replaces all data.
- PATCH updates part of the data.
- DELETE removes data.
- An Endpoint is a URL plus an HTTP method.
- Path Parameters identify one resource.
- Query Parameters filter or sort data.
- The Request Body sends data to the server.
- Status Codes tell if the request succeeded or failed.
- Headers describe the request or response.

---