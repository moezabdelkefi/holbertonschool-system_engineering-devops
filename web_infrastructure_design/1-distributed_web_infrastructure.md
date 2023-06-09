<h1 align="center">Simple web stack</h1>

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
                   |                         |
                   +-----+---------------+---+
                         |               |
         6. Load Balancing Algorithm | 6. Load Balancing Algorithm
                         |               |
         +---------------v---------------v-----+
         |                                     |
         |   Web Server (Nginx)                 |
         |   Application Server                 |
         |                                     |
         +---------------+---------------------+
                         |
          7. Load Balanced Traffic
                         |
         +---------------v---------------------+
         |                                     |
         |   Web Server (Nginx)                 |
         |   Application Server                 |
         |                                     |
         +---------------+---------------------+
                         |
          7. Load Balanced Traffic
                         |
         +---------------v---------------------+
         |                                     |
         |   Database Server (MySQL)           |
         |   Primary-Replica Cluster           |
         |                                     |
         +-------------------------------------+


## For every additional element, why you are adding it:
Two additional servers are added to distribute the load, increase scalability, and handle higher traffic volume.
A load balancer (HAproxy) is added to evenly distribute incoming traffic across the multiple web servers, improving performance and preventing overload on a single server.
An application server is added to separate the web server functionality from the application logic, allowing for better scalability, maintenance, and code organization.
A primary-replica database cluster is introduced to provide fault tolerance, data redundancy, and increased read performance.

## Load balancer distribution algorithm and how it works:

The load balancer (HAproxy) can be configured with various distribution algorithms, such as round-robin or least connections

## Active-Active vs. Active-Passive setup:
Active-Active setup where both web servers actively handle incoming traffic simultaneously. In an Active-Passive setup, one server would be actively serving traffic, while the other would remain on standby as a backup. Active-Active offers higher availability and better load distribution.

## Database Primary-Replica (Master-Slave) cluster:
enables data from one database server (the master) to be replicated to one or more other database servers (the slaves). 

## Difference between Primary and Replica nodes in regard to the application:
while the number of primary shards cannot be changed after the index has been created, the number of replicas can be altered at any time.
