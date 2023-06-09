<h1 align="center">Simple web stack</h1>

                                                        +------------------------+
                                                        |                        |
                                                        |   User's Web Browser   |
                                                        |                        |
                                                        +----+--------------+----+
                                                            |              |
                                                    3. Domain Configuration |
                                                            |              |
                                                        +----v--------------v----+
                                                        |                        |
                                                        |   Domain Registrar     |
                                                        |   www.foobar.com       |
                                                        +----+--------------+----+
                                                            |              |
                                                    4. Domain Configuration |
                                                            |              |
                                                        +----v--------------v----+
                                                        |                        |
                                                        |  DNS Provider (e.g.,    |
                                                        |  Cloudflare, Route 53) |
                                                        |                        |
                                                        +----+--------------+----+
                                                            |              |
                                                    5. DNS Configuration   |
                                                            |              |
                                                        +----v--------------v----+
                                                        |                        |
                                                        |   Server (8.8.8.8)      |
                                                        |                        |
                                                        +----+--------------+----+
                                                            |              |
                                                    6. Server Setup        |
                                                            |              |
                                                        +----v--------------v----+
                                                        |                        |
                                                        |   Web Server (Nginx)    |
                                                        |   Application Server   |
                                                        |   Database (MySQL)     |
                                                        |                        |
                                                        +------------------------+

## Server:
A server is a computer or system that provides services or resources to other computers

## Domain name:
The domain name is a human-readable address that represents the IP address of the server hosting a website. It allows users to access websites using a memorable name instead of a string of numbers (IP address). In this case, the domain name "www.foobar.com" is configured to point to the server's IP address (8.8.8.8).

## Type of DNS record is www in www.foobar.com:
The "www" in "www.foobar.com" is a subdomain. It is a commonly used prefix to indicate the World Wide Web service of a domain. In DNS, it is typically represented as a CNAME (Canonical Name) record that points to the main domain, foobar.com.

## Role of the web server:
The web server, in this case, Nginx, handles incoming HTTP requests from users' web browsers and serves static files such as HTML, CSS, JavaScript, and images

## The role of the application server:
The application server is responsible for executing the application code and generating dynamic content for the website. It hosts the code base of the web application and handles business logic and other

## The role of the database:
The database stores and manages structured data for the web application. In this case, MySQL is used as the database system.

## What is the server using to communicate with the user's computer requesting the website?
The server communicates with the user's computer over the Hypertext Transfer Protocol (HTTP) or, if configured with SSL/TLS certificates, over HTTPS. When a user requests a website, their web browser sends an HTTP request to the server, which responds with the appropriate web content.

### The issues with this infrastructure:

## ingle Point of Failure (SPOF):
.Adding a backup server or using load balancing techniques to distribute traffic across multiple servers.

## Downtime during maintenance:
a machine is not operating or being productive due to required maintenance work.

## nability to scale with high incoming traffic:
With a single server, this infrastructure may struggle to handle a significant increase in incoming traffic. Scaling can be achieved by introducing load balancers to distribute traffic across multiple servers or by using cloud-based solutions that offer auto-scaling capabilities based on traffic demand.




