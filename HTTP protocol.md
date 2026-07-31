HTTP (Hypertext Transfer Protocol) is the foundational application-layer protocol used for structured communication
between clients (like web browsers) and servers over the internet.  It operates on a stateless request-response 
model where the client initiates a message to retrieve resources or trigger actions, and the server processes the 
request and returns a response containing a status code, headers, and an optional body.

## Structure of an HTTP Request
  
  ### Every HTTP request consists of three main components:

    Request Line: Specifies the HTTP method (verb), the resource path (URI/URL), and the protocol version 
      (e.g., GET /index.html HTTP/1.1). 
    Headers: Provide metadata such as the host domain, user-agent, accepted content types, and authorization tokens.
      Host: api.example.com
      User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36
      Accept: application/json
      Accept-Language: en-US,en;q=0.9
      Accept-Encoding: gzip, deflate
      Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
      Cookie: session_id=abc123; theme=dark
      Connection: keep-alive
    Body: An optional section used to send data to the server, commonly found in POST, PUT, or PATCH requests. 
  
## Common HTTP Methods Clients use specific methods to define the desired action on a resource:

  **GET**: Retrieves data from the server; it is safe and idempotent.  
  **POST**: Sends data to the server to create or update a resource; it is not        idempotent.  
  **PUT**: Completely replaces an existing resource or creates a new one; it is       idempotent.  
  **DELETE**: Removes a specified resource from the server; it is idempotent.  
  **PATCH**: Applies partial modifications to a resource.  
  **HEAD**: Retrieves only the headers of a resource without the body, useful for checking metadata.  
  **OPTIONS**: Describes the communication options available for a resource.

**HTTP vs. HTTPS** 
  Standard HTTP sends data in plain text, making it vulnerable to interception.
  HTTPS (HTTP Secure) encrypts all communication using SSL/TLS, ensuring data confidentiality and integrity, 
  which is essential for sensitive transactions like logins and payments. While HTTP relies on TCP for reliable delivery,
  HTTPS adds a security layer through a TLS handshake before data exchange begins

## HTTP request
### HTTP response codes
HTTP response status codes are three-digit numbers sent by a server to indicate the result of an HTTP request.

They are categorized into five classes based on the first digit:

  **1xx Informational**: The request was received and is being processed
    (e.g., 100 Continue, 101 Switching Protocols). 
  **2xx Success:** The request was successfully received, understood, and accepted 
    (e.g., 200 OK, 201 Created, 204 No Content). 
  **3xx Redirection**: Further action is required to complete the request, typically URL redirection 
    (e.g., 301 Moved Permanently, 302 Found, 304 Not Modified). 
  **4xx Client Error**: The request contains bad syntax or cannot be fulfilled by the client 
    (e.g., 400 Bad Request, 401 Unauthorized, 403 Forbidden, 404 Not Found). 
  **5xx Server Error**: The server failed to fulfill a valid request due to an internal error 
    (e.g., 500 Internal Server Error, 502 Bad Gateway, 503 Service Unavailable). 

These codes serve as a universal handshake between clients and servers, allowing developers to quickly identify whether
a request succeeded, requires client correction, or indicates server-side issues.
