<h1 align="center">Scale up</h1>

      
                                                +-------------------------+
                                                |                         |
                                                |   User's Web Browser    |
                                                |                         |
                                                +-----------+-------------+
                                                            |
                                                    3. DNS Resolution
                                                            |
                                                +-----------v-------------+
                                                |                         |
                                                |   DNS Provider          |
                                                |                         |
                                                +-----+---------------+---+
                                                        |               |
                                        4. DNS Resolution | 4. DNS Resolution
                                                        |               |
                                                +-----v---------------v---+
                                                |                         |
                                                |   Load Balancer         |
                                                |   (HAproxy)             |
                                                |   (Clustered)           |
                                                +-----+---------------+---+
                                                        |               |
                                    6. Load Balancing Algorithm | 6. Load Balancing Algorithm
                                                        |               |
                                    +---------------v---------------v-----+
                                    |                                     |
                                    |   Web Server (Nginx)                 |
                                    |                                     |
                                    +---------------+---------------------+
                                                        |
                                    +---------------v---------------+
                                    |                               |
                                    |   Application Server           |
                                    |                               |
                                    +---------------+---------------+
                                                        |
                                    +---------------v---------------+
                                    |                               |
                                    |   Database Server (MySQL)     |
                                    |                               |
                                    +-------------------------------+

## For every additional element, why you are adding it:
One additional server is added to separate the components (web server, application server, and database) onto their own servers, allowing for better resource allocation, scalability, and fault isolation.
The load balancer (HAproxy) is configured as a cluster with the existing load balancer. This ensures high availability and redundancy, so if one load balancer fails, the other can continue handling incoming traffic seamlessly.

## Web Server: 
The web server (Nginx) is responsible for handling HTTP requests, serving static files, and potentially handling SSL termination. By dedicating a separate server for the web server, it allows for efficient handling of web-related tasks and improved performance.

## Application Server: 
The application server handles the dynamic processing of requests, executes the business logic, and interacts with the database. Separating it onto its own server allows for better resource management and scalability, as it can be optimized specifically for application-related tasks.

## Database Server: 
The database server (MySQL) stores and manages the website's data. By having a dedicated server for the database, it ensures efficient data storage, retrieval, and management, enabling scalability and optimizing performance.

## The load balancer (HAproxy) is configured as a cluster:

Load Balancer (HAproxy): The load balancer distributes incoming traffic across multiple servers, improving scalability, performance, and fault tolerance. Configuring it as a cluster with the existing load balancer ensures redundancy and high availability, as if one load balancer fails, the other can take over seamlessly.