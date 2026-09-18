# How the Web Works

## What is the Web?

The Web is a system that allows users to access websites and web applications through the Internet.

A browser acts as the **client**, while a web server provides the requested resources.

Basic flow:

**Browser → Request → Web Server → Response → Browser**

---

## Client

The **client** is usually your web browser.

Examples:

* Chrome
* Firefox
* Edge

The browser sends requests to web servers and displays the responses.

---

## Web Server

A **web server** receives requests from clients and sends back responses.

It can provide:

* HTML
* CSS
* JavaScript
* Images
* API data

---

## HTTP

**HTTP (Hypertext Transfer Protocol)** is used for communication between the browser and web server.

Example request:

```http
GET /index.html HTTP/1.1
Host: example.com
```

The server then sends an HTTP response.

---

## HTTPS

**HTTPS** is HTTP protected with **TLS encryption**.

HTTP:

* Data is sent without encryption.

HTTPS:

* Data is encrypted during transmission.

Most modern websites use HTTPS.

---

## DNS

Before the browser can connect to a domain, it needs to find the server's IP address.

DNS translates:

```text
example.com → IP address
```

Basic flow:

**Domain → DNS → IP address → Web Server**

---

## URL

A URL identifies a resource on the Web.

Example:

```text
https://example.com/login
```

Parts:

* `https` → protocol
* `example.com` → domain
* `/login` → path

---

## HTTP Request

A request is sent from the client to the server.

It can contain:

* Method
* URL/path
* Headers
* Cookies
* Body

Common methods:

```text
GET  → request data
POST → send data
```

---

## HTTP Response

The server sends a response back to the client.

Example:

```http
HTTP/1.1 200 OK
Content-Type: text/html
```

Common status codes:

```text
200 → OK
301/302 → Redirect
400 → Bad Request
401 → Unauthorized
403 → Forbidden
404 → Not Found
500 → Server Error
```

---

## Cookies

Cookies are small pieces of data stored by the browser.

They are commonly used for:

* Login sessions
* User preferences
* Tracking

Example:

```http
Set-Cookie: session=abc123
```

The browser can later send:

```http
Cookie: session=abc123
```

---

## HTML, CSS and JavaScript

Websites commonly use three main technologies:

**HTML** → structure/content

**CSS** → appearance/style

**JavaScript** → functionality/behavior

Example:

```text
HTML       → button exists
CSS        → button looks good
JavaScript → button does something when clicked
```

---

## Web Application

A web application is more than a static website.

Examples:

* Login systems
* Online shops
* Banking applications
* Social media
* Web APIs

Web applications usually have a **frontend** and **backend**.

```text
Browser
   ↓
Frontend
   ↓
HTTP Request
   ↓
Backend
   ↓
Database
```

---

## Important for Cybersecurity

When testing a web application, it is important to understand the normal communication first.

Typical attack surface:

```text
Browser
   ↓
HTTP/HTTPS
   ↓
Web Server
   ↓
Web Application
   ↓
Database
```

Things a pentester may investigate include:

* HTTP requests and responses
* Parameters
* Cookies
* Authentication
* Headers
* URLs
* Forms
* APIs
* Input handling

---

## Key Things to Remember

* Browser = client
* Server = provides resources/services
* HTTP = communication protocol
* HTTPS = HTTP + TLS encryption
* DNS = domain → IP
* URL = address of a web resource
* Request = client → server
* Response = server → client
* Cookie = data stored by the browser
* HTML = structure
* CSS = style
* JavaScript = functionality
* Web application = frontend + backend + often database
