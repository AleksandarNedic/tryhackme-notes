# HTTP Details

## What is HTTP?

HTTP (Hypertext Transfer Protocol) is a protocol used for communication between a **web browser/client and a web server**.

For example:

```text
Browser → HTTP Request → Web Server
Browser ← HTTP Response ← Web Server
```

HTTP is used when accessing websites and web applications.

---

## HTTP Request

When you visit a website, your browser sends an HTTP request to the server.

A request can contain:

* Method
* URL/path
* Headers
* Cookies
* Body

Example:

```http
GET /index.html HTTP/1.1
Host: example.com
User-Agent: Chrome
Cookie: session=abc123
```

---

## HTTP Methods

### GET

Used to **request data** from a server.

```http
GET /index.html HTTP/1.1
```

For example, loading a webpage usually involves GET requests.

### POST

Used to **send data** to the server.

For example, submitting a login form:

```http
POST /login HTTP/1.1
```

The username and password may be sent in the request body.

---

## HTTP Response

After receiving a request, the server sends a response.

Example:

```http
HTTP/1.1 200 OK
Content-Type: text/html
```

The response can contain:

* Status code
* Headers
* Cookies
* Response body

---

## HTTP Status Codes

Status codes tell us what happened with the request.

### 2xx — Success

```text
200 OK
```

The request was successful.

### 3xx — Redirection

```text
301 Moved Permanently
302 Found
```

The client is redirected somewhere else.

### 4xx — Client Error

```text
400 Bad Request
401 Unauthorized
403 Forbidden
404 Not Found
```

The request could not be completed because of a client/request-related issue or access restriction.

### 5xx — Server Error

```text
500 Internal Server Error
```
