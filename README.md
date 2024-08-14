# What is the Project
![Project Management Tool Homepage](https://i.ibb.co/wpKt0vZ/PPMT.png)
This App is a ReactJS and Springboot App which allows the user to manage projects

# Stack

1.  ReactJS
-   React Components
-   HTTP Client using axios Library
-   Basic react Routing
-   React Bootstrap
-   Communication between React Components

2.  SpringBoot
-   Springboot RestController
-   Service, Repository(DAO) from Spring Framework
-   Autowiring is used as well to inject the Dependencies

3. JSON Web Tokens for Authentication


**ppmtool-react-client**  : This has the Client Code implemented using React JS

**project_management_tool**  : This has the Springboot code

**pom.xml**  : This is multimodule pom. This pom in turn executes the pom within the client and the server folders

# Application Design

### ReactJS

1.  **Project**  Component : This Component allows us to add and update projects
    
2.  **Project Board**  Component : This Component allows us to add and update project tasks and backlogs and takes care of updating the project board. 
3. **User Management**  Component : This Component takes care of registering and loggin-in a user.


#### HTTP client

**axios**  library is used to make HTTP Calls

The application has just one url /customerlist which ties to  _Customers_  Component

### SpringBoot

The package  `com.example.project_management_tool`  has the  `ProjectManagementToolApplication.java`  file which ensures that the application runs in an embedded container and forms the starting point of the code

 1. **Domains**

The package  `com.example.project_management_tool.domain` defines all the Java models for the project. 
 - Backlog
 - Project
 - ProjectTask
 - User

2. **Exceptions**
The package  `com.example.project_management_tool.exceptions`  has the custom exception logic and response logic defined for the following exceptions.
 - Custom Response Entity Exception
 - Invalid Login Response
 - Project Id Exception
 - Project Not Found Exception
 - UserName already exists Exception

3. **Repositories**
The package  `com.example.project_management_tool.repositories`  has the repositories for CRUD operations defined. 
 - Backlog Repository
 - Project Repository
 - Project Task Repository
 - User Repository

4. **Services**
The package  `com.example.project_management_tool.services`  has the services defined and has the logic for the below tasks. The  **Service**  is where the business logic is run on the Data which comes from DAO
 - Custom User Details Service
 - Map Validation Error Service
 - Project Service
 - Project Task Service
 - User Service

5. **Controllers**
The package  `com.example.project_management_tool.web`  has the Rest Controller defined. The controller has all the end points defined and mentions which function should be executed when an end point is called. The Controller also defines which Endpoint Calls which Service. 
 - Backlog Controller
 - Project Controller
 - User Controller

6. **Payload**
The package  `com.example.project_management_tool.payload`  handles login request and the JWT login response.


The  `application.properties`  file is used to define various properties such as the port in which the embedded container runs , the context path of the application etc