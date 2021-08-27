## Lecture 2 Software Engineering Principles

#### Assignment 0 instructions

- Git good

#### Web Development Overview

- Essentially a client-server architecture
- Client - Server that runs on top of a backend

Browser 
- HTML Renderer
- Javascript Interpreter 
- XML or JSON

Native App
- XML, JSON

HTTP Server Side
- Listens to and respond to requests

Servers (back-ends) contain the persistent data, and most of the business logic
- Servers answer client requests
- Servers contain many pieces:
  - HTTP server
  - Business Logic
  - Databases
  - Caches
  - Load balancers

Browser
- The user interface
- Gets and sends data to/from the backend
- Technologies: HTML, CSS, JS

Network
- The transport (HTTP, URI, REST)

Backend
- Stores and processes data
- Critical processing
- Flask, Django, etc..

HTML (hyper-text markup language)
- A declaritive language to describe content

CSS (cascading style sheets)
- A declarative language to describe the presentation of content

Javascript
- An imperative language to describe functionality
- Changes content and presentation and issues data requests to backend

HTTP - Web Transfer Protocol

- A protocol specifying requests (from client) and responses (from server)
  - Built on top of TCP (reliable stream of bytes)

#### EXAMPLE REQUEST

Flask: "GET / HTTP/1.1" 200
Flask: "POST / HTTP/1.1" 404

*REQUEST:*
GET /index.html HTTP/1.1
User-agent: Safari 4.0
Referrer: http://test.com/testpage.html
If-modified-since: Fri, 31 Dec 2016 23:59:58    - (this is a caching hint)
[blank line]

RESPONSE:
HTTP/1.1 200 OK
Date: Fri, 31 Dec 2016 00:01:45
Content-type: text/html
Content-Length: 19
[blank line]
<html>Hello</html>

Codes: 
200 -> OK
3xx -> alternative (redirected, cache)
4xx, 5xx -> Errors


URL = Uniform Resource Loader
- Identifies files/resources available from web servers

Example: http://server.com:8888/path/file?p1=v1&p2=v2#x
- Protocol (scheme): http, https
- Host: server.com
- Port: 8888 (optional, default 80)
- Path: /path/file
- Query: p1=v1&p2=v2 (optional)


Rest (Representational State Transfer)

- Principles for designing URL-based addressing
