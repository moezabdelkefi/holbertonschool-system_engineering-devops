   <h1 align="center">ecured and monitored web infrastructure</h1>

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
                                                    |   Firewall                           |
                                                    |                                     |
                                                    +---------------+---------------------+
                                                                        |
                                                    +---------------v---------------+
                                                    |                               |
                                                    |   Web Server (Nginx)           |
                                                    |   Application Server           |
                                                    |                               |
                                                    +---------------+---------------+
                                                                        |
                                                    +---------------v---------------+
                                                    |                               |
                                                    |   Firewall                     |
                                                    |                               |
                                                    +---------------+---------------+
                                                                        |
                                                    +---------------v---------------+
                                                    |                               |
                                                    |   Web Server (Nginx)           |
                                                    |   Application Server           |
                                                    |                               |
                                                    +---------------+---------------+
                                                                        |
                                                    +---------------v---------------+
                                                    |                               |
                                                    |   Firewall                     |
                                                    |                               |
                                                    +---------------+---------------+
                                                                        |
                                                    +---------------v---------------+
                                                    |                               |
                                                    |   Database Server (MySQL)     |
                                                    |                               |
                                                    +---------------+---------------+
                                                                        |
                                                    +---------------v---------------+
                                                    |                               |
                                                    |   Monitoring Client            |
                                                    |                               |
                                                    +---------------+---------------+
                                                                        |
                                                    +---------------v---------------+
                                                    |                               |
                                                    |   Monitoring Client            |
                                                    |                               |
                                                    +---------------+---------------+
                                                                        |
                                                    +---------------v---------------+
                                                    |                               |
                                                    |   Monitoring Client            |
                                                    |                               |
                                                    +-------------------------------+

## For every additional element, why you are adding it:
Three firewalls are added to enhance security by filtering and monitoring incoming and outgoing network traffic, protecting the infrastructure from unauthorized access and potential threats.
An SSL certificate is added to enable HTTPS and serve encrypted traffic between the web server and the user's web browser, ensuring secure communication and protecting sensitive information.
Three monitoring clients (data collectors) are added to collect and send monitoring data to a monitoring service (such as Sumo Logic). They provide visibility into the infrastructure's performance, availability, and security.

## What firewalls are for:

Firewalls act as a security barrier, monitoring and controlling network traffic based on predetermined security rules. They protect the infrastructure from unauthorized access, malware, and other malicious activities by filtering incoming and outgoing traffic.

## Why traffic is served over HTTPS:

Traffic is served over HTTPS to provide secure communication between the user's web browser and the web server. HTTPS encrypts the data exchanged, ensuring confidentiality and integrity, and protecting sensitive information such as login credentials, payment details, and user privacy.

## What monitoring is used for:

Monitoring is used to observe and track the performance, availability, and security of the infrastructure. It helps identify issues, troubleshoot problems, and ensure the smooth operation of the system. Monitoring can provide insights into resource utilization,