## **# 1 - Tier Architecture**

- All components—client, server, and database—are hosted on a single machine.
- The user interacts directly with the database without any intermediary layers.
- Commonly used in standalone or personal applications where data access is limited to a single user or system.

![img1.png](IT%20Fundamentals/Database%20Management%20System/Introduction/Images/img3.png)

## **# 2 - Tier Architecture**

- Follows a client-server model.
- The application (client) communicates directly with the database (server) using an API or database driver.
- Application and database reside on different machines.
- Comprises two layers:
    - **Tier 1 – Client Layer**: User interface and business logic
    - **Tier 2 – Database Layer**: Data storage and management

![image.png](IT%20Fundamentals/Database%20Management%20System/Introduction/Images/img1.png)

## **# 3 - Tier Architecture**

- Introduces an intermediate **application server** between the client and the database.
- The client interacts with the application server, which in turn communicates with the database server.
- Enhances scalability, security, and maintainability.
- Comprises three layers:
    - **Tier 1 – Client Layer**: User interface
    - **Tier 2 – Application Layer**: Business logic
    - **Tier 3 – Database Layer**: Data storage and management

![image.png](IT%20Fundamentals/Database%20Management%20System/Introduction/Images/img2.png)