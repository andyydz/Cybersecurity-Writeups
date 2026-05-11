# HTTP in Detail | TryHackMe Write-up

In this room, I learned how HTTP and HTTPS actually work behind the scenes when we visit websites. Before this, I only knew that HTTP is used for websites, but now I understand how requests, responses, headers, cookies, and status codes work together during communication between a browser and a server.

---

# Task 1 — What is HTTP(S)?

This task explained the basics of HTTP and HTTPS.

HTTP stands for HyperText Transfer Protocol. It is the protocol used for communication between a browser and a web server.

HTTPS is basically the secure version of HTTP. The main difference is that HTTPS encrypts the communication using SSL/TLS so attackers cannot easily read the data being transferred.

For example:

- HTTP → data is transferred in plain text
- HTTPS → data is encrypted

That is why websites with login pages or payment systems use HTTPS.

### Main things I learned

- HTTP is used for web communication
- HTTPS adds encryption and security
- HTTPS protects sensitive information
- Browsers and servers communicate using requests and responses

---

# Task 2 — Requests And Responses

This section explained how browsers and servers communicate.

When we visit a website, the browser sends an HTTP request to the server, and the server sends back an HTTP response.

### Example

Browser request:

```http
GET / HTTP/1.1
Host: example.com
```

Server response:

```http
HTTP/1.1 200 OK
```

I learned that requests contain information like:

- Request method
- URL
- Headers

And responses contain:

- Status codes
- Headers
- Website content

This task made the communication process much easier to understand.

---

# Task 3 — HTTP Methods

This task explained different HTTP methods and what they are used for.

### GET
Used to request data from a server.

Example:
Opening a webpage.

### POST
Used to send data to a server.

Example:
Submitting a login form.

### PUT
Used to update existing data.

### DELETE
Used to remove data.

I learned that different methods tell the server what kind of action the client wants to perform.

---

# Task 4 — HTTP Status Codes

This section explained HTTP status codes.

I already saw some of these codes before, but now I understand what they actually mean.

### Common Status Codes

### 200 OK
Request was successful.

### 301 Moved Permanently
Page has been redirected.

### 404 Not Found
Requested page does not exist.

### 500 Internal Server Error
Something went wrong on the server side.

I learned that status codes are grouped into categories:

- 100 → Informational
- 200 → Success
- 300 → Redirection
- 400 → Client errors
- 500 → Server errors

---

# Task 5 — Headers

This task explained HTTP headers.

Headers contain additional information about requests and responses.

### Examples

```http
User-Agent
Cookie
Content-Type
```

I learned that headers help browsers and servers exchange extra details like browser type, content format, authentication, cookies, and more.

This section also helped me understand why headers are important in web security and web testing.

---

# Task 6 — Cookies

This section explained how cookies work.

Cookies are small pieces of data stored in the browser to remember information about users.

For example:

- Keeping users logged in
- Remembering preferences
- Session management

Without cookies, websites would forget users every time they refresh the page.

I also learned that cookies can sometimes become a security issue if not handled properly.

---

# Task 7 — Making Requests

In this practical task, I worked with HTTP requests directly and observed how servers respond.

This helped me understand how web communication works in real scenarios instead of only reading theory.

### What I practiced

- Sending HTTP requests
- Understanding responses
- Observing headers and status codes
- Basic web communication analysis

---

# Final Thoughts

Overall, this room gave me a much better understanding of how websites communicate using HTTP and HTTPS.

Before this room, I only knew basic things about websites, but now I understand:

- How requests and responses work
- Different HTTP methods
- Status codes
- Headers
- Cookies
- Difference between HTTP and HTTPS

This room was beginner-friendly and very useful for understanding web fundamentals and cybersecurity basics.
