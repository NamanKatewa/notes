**Hypertext Transfer Protocol**

- Set of rules for the exchange of information over the internet
- Responsible for communication between web servers & clients

**HTTPS - Hypertext Transfer Protocol Secure**

- Used for secure communication
- Encrypted using TLS (Transport Layer Security), SSL (Secure Sockets Layer)

## HTTP Request

- Sent by the client to initiate communication with the server

**Components -**

### Request Line

- **Method**
	GET POST PUT DELETE HEAD etc.
- **URL / Path**
	The resource being requested
- **HTTP Version**
	Version of HTTP used

### Headers

- Additional information about the request , eg - browser type, accepted file formats, encoding

### Body (Optional)

- Contains the data being sent

## HTTP Response

- The serves receives the request, processes it, and send back a response.
- Contains the status & the requested data or error message

**Components -**

### Status Line

#### HTTP Version

- The version of the protocol used

#### Status Code

- Indicates the result of the request

#### Reason Phrase

- Human readable explanation of the status code

### Headers

- Info about the response, content type, length, server info

### Body

- The content requested by the client.
- Can be empty


## Common HTTP Status Codes

### 1xx Informational
	Request received, processing continues
	100 Continue
## 2xx Success
	Request successfully received, understood, and accepted
	200 OK
	201 Created
### 3xx Redirection
	Further action needed
	301 Moved Permanently
	302 Found
### 4xx Client Error
	Request contains bad syntax or cannot be fulfilled
	400 Bad Request
	404 Not Found
## 5xx Server Error
	Server failed to fulfill
	500 Internal Server Error
	503 Service Unavailable