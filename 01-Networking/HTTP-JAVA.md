This lesson explains how **Java applications send HTTP requests** using the built-in **HttpClient** (Java 11+).

---

## 1. What is Java HttpClient?

`HttpClient` is Java's modern class for sending HTTP requests.

Before Java 11, developers mostly used:

- HttpURLConnection
- Apache HttpClient
- RestTemplate

Java 11 added a new standard **HttpClient** with support for HTTP/2 and asynchronous requests.

---

## 2. Three Main Classes

### HttpClient

Sends requests.

---

### HttpRequest

Represents the request.

It contains:

- URL
- Method
- Headers
- Body

---

### HttpResponse

Represents the server's response.

It contains:

- Status Code
- Headers
- Body

These are the three core classes of the API.

---

## 3. Creating a Request

First, create the request.

Example:

```java
HttpRequest request = HttpRequest.newBuilder()
    .uri(new URI("https://example.com"))
    .GET()
    .build();
```

You must provide:

- URI
- HTTP Method

---

## 4. Choosing the HTTP Version

By default, Java tries to use **HTTP/2**.

You can also choose the version yourself.

Example:

```java
.version(HttpClient.Version.HTTP_2)
```

If the server does not support HTTP/2, Java automatically uses HTTP/1.1.

---

## 5. Adding Headers

Headers give extra information.

Example:

```java
.header("Content-Type", "application/json")
```

or

```java
.headers("key1","value1","key2","value2")
```

---

## 6. Setting a Timeout

You can choose how long to wait for a response.

Example:

```java
.timeout(Duration.ofSeconds(10))
```

If the server takes too long, Java throws a timeout exception.

---

## 7. Sending a Request Body

For methods like:

- POST
- PUT

You send data in the body.

Example:

```java
HttpRequest.BodyPublishers.ofString(json)
```

Java can also send:

- String
- File
- Byte Array
- InputStream

---

## 8. Creating HttpClient

Create the client once.

Example:

```java
HttpClient client = HttpClient.newHttpClient();
```

The client is responsible for sending requests.

---

## 9. Reading the Response

Example:

```java
HttpResponse<String> response =
    client.send(request, BodyHandlers.ofString());
```

You can read:

```java
response.statusCode();
```

and

```java
response.body();
```

---

## 10. Synchronous Request

A synchronous request waits for the response.

Example:

```java
client.send(request, BodyHandlers.ofString());
```

Your program stops until the server replies.

---

## 11. Asynchronous Request

An asynchronous request does **not** wait.

Example:

```java
client.sendAsync(request, BodyHandlers.ofString());
```

It returns a **CompletableFuture**.

Your program can continue doing other work while waiting for the response.

---

## 12. Authentication

Some servers require:

- Username
- Password

Java HttpClient supports authentication using an `Authenticator`.

---

## 13. Redirects

Sometimes a page moves to another URL.

The client can automatically follow redirects.

Example:

```java
.followRedirects(HttpClient.Redirect.ALWAYS)
```

---

## 14. Cookies

HttpClient can store and send cookies.

This helps keep user sessions.

---

## 15. HTTP/2 Push Promise

HTTP/2 allows the server to send extra resources before the client asks for them.

This can make websites load faster.

Java HttpClient supports this feature.

---

# Key Points to Remember

- Java 11 introduced a modern **HttpClient**.
- The three main classes are:
    - `HttpClient`
    - `HttpRequest`
    - `HttpResponse`
- `HttpRequest` contains URI, method, headers, and body.
- `HttpClient` sends the request.
- `HttpResponse` contains status code, headers, and body.
- Java supports HTTP/1.1 and HTTP/2.
- Requests can be **synchronous** or **asynchronous**.
- `BodyPublisher` sends request data.
- `BodyHandler` reads response data.
- Java HttpClient supports redirects, cookies, authentication, and HTTP/2 features.

---