# What is Spring Boot?
->Spring Boot is a Java framework used to create applications easily. It is based on the Spring Framework. It provides features like auto-configuration, starter dependencies, and an embedded server. We can use Spring Boot to create web applications and REST APIs.

# What are the main features of Spring Boot?
-> Auto Configuration – It automatically configures many things for our application.
Starter Dependencies – They provide the required libraries easily.
Embedded Server – We can run the application without installing a separate server.
Spring Boot Actuator – It helps us check and monitor the application.
Less Configuration – We need to write less configuration code

# What is Spring Boot Auto Configuration?
->Auto Configuration means Spring Boot automatically sets up the required configuration for our application based on the dependencies we add to the project. It reduces the amount of configuration we need to write manually

# What is @SpringBootApplication in Spring Boot?
-> @SpringBootApplication is an important annotation in Spring Boot. We usually put it on the main class of the application. It tells Spring Boot to start the application and do the required configuration automatically
@SpringBootApplication is a combination of three annotations:
@Configuration
@EnableAutoConfiguration
@ComponentScan

# What is the difference between Spring and Spring Boot?
->Spring is a framework for building Java applications, while Spring Boot is built on Spring and makes development easier by providing auto-configuration, starter dependencies, and an embedded server.

# What is Dependency Injection in Spring Boot?
->Dependency Injection is a process where Spring creates the required objects and gives them to the class that needs them. It helps us avoid creating objects manually.

# What is a Spring Bean?
-> A Spring Bean is an object that is created and managed by the Spring Framework. Spring creates the object, keeps it, and gives it to other classes when they need it.

# What is the Spring IoC Container?
->IoC stands for Inversion of Control. The Spring IoC Container creates and manages objects called Beans. It also gives these objects to other classes when they are needed

# What is the difference between IoC and Dependency Injection?
-> IoC means Spring takes control of creating and managing objects instead of us creating them. Dependency Injection is the way Spring gives those objects to the classes that need them.

# What is @Autowired in Spring Boot?
-> @Autowired is used to inject a required object into a class. Spring finds the required Bean and gives it to the class

# What is the difference between @Component, @Service, and @Repository?
-> @Component is used for a general class, @Service is used for business logic, and @Repository is used for database operations. All three are managed by Spring.

# What is @RestController in Spring Boot?
-> @RestController is an annotation used to create REST API controllers in Spring Boot. It is used to handle HTTP requests such as GET, POST, PUT, and DELETE. The data returned by its methods is directly sent to the client, usually in JSON format. @RestController is a combination of @Controller and @ResponseBody.

# What is the difference between @Controller and @RestController?
->@Controller is used to create a controller that usually returns a view such as an HTML page. @RestController is used to create REST APIs and usually returns data such as JSON. @RestController is a combination of @Controller and @ResponseBody. So, for REST APIs, we normally use @RestController.

# What is @RequestMapping in Spring Boot?
-> @RequestMapping is used to map an HTTP request to a controller class or method. It defines the URL path and can also specify the HTTP method such as GET, POST, PUT, or DELETE. We can use it at the class level or method level. For example, @RequestMapping("/employees") means requests with the /employees path will be handled by that controller or method.

# What is the difference between @GetMapping, @PostMapping, @PutMapping, and @DeleteMapping?
->These annotations are used to handle different HTTP requests in Spring Boot. @GetMapping is used to get or retrieve data, @PostMapping is used to create or send new data, @PutMapping is used to update existing data, and @DeleteMapping is used to delete data. These annotations are shorter and easier versions of @RequestMapping with a specific HTTP method.

# What is @RequestBody in Spring Boot?
->@RequestBody is used to get data from the body of an HTTP request and convert that data into a Java object. It is commonly used with POST and PUT requests. For example, when the client sends employee data in JSON format, @RequestBody converts that JSON data into an Employee object so we can use it in our application.

# What is @PathVariable in Spring Boot?
->@PathVariable is used to get a value from the URL path and use it inside a controller method. For example, if the URL is /employees/101, then 101 is the employee ID. We can use @PathVariable to get this ID and use it to find the employee from the database.

# What is @RequestParam in Spring Boot?
->@RequestParam is used to get a value from the query parameter of a URL. For example, if the URL is /employees?id=101, we can use @RequestParam to get the value 101. It is commonly used when we need to pass small values like ID, name, or page number through the URL.

# What is @RequestMapping vs @GetMapping?
->@RequestMapping is a general annotation used to map a URL to a controller method or class. We can use it with different HTTP methods like GET, POST, PUT, and DELETE. @GetMapping is specifically used for GET requests. So, @GetMapping is a shorter and more specific way to handle GET requests.

# What is @RequestParam vs @PathVariable?
->@RequestParam is used to get a value from the query parameter of the URL, while @PathVariable is used to get a value from the URL path. For example, in /employees?id=101, we use @RequestParam to get 101. In /employees/101, we use @PathVariable to get 101. So, @RequestParam is used for query parameters, and @PathVariable is used for values inside the URL path.

# What is @Service in Spring Boot?
-> @Service is an annotation used on a class that contains the business logic of an application. It tells Spring to create and manage an object of that class as a Spring Bean. The service layer usually receives requests from the controller, performs the required business logic, and communicates with the repository when database operations are needed. It helps us keep the business logic separate from the controller and repository.

# What is @Repository in Spring Boot?
-> @Repository is an annotation used for classes that handle database operations. It tells Spring to create and manage that class as a Spring Bean. The repository layer is responsible for operations like saving, finding, updating, and deleting data from the database. It also helps Spring handle certain database-related exceptions.

# What is @Component in Spring Boot?
->@Component is an annotation used to tell Spring that this class should be managed by the Spring container. Spring creates an object of the class and manages its life cycle. We use @Component for general-purpose classes that do not specifically belong to the service, repository, or controller layer. It also allows Spring to inject this object into other classes when required.

# What is Spring Boot Starter?
->Spring Boot Starter is a group of dependencies that provides the libraries needed for a particular feature. Instead of adding each library separately, we can add one starter dependency and Spring Boot provides the required libraries. For example, spring-boot-starter-web provides the libraries needed to create web applications and REST APIs. It makes dependency management easier.

# What is an Embedded Server in Spring Boot?
->An embedded server is a server that is already included in a Spring Boot application. We normally use servers like Tomcat to run our web application. In Spring Boot, Tomcat is included by default with the web starter, so we do not need to install and configure a separate server. We can simply run the Spring Boot application, and it starts the embedded server automatically. By default, Tomcat runs on port 8080.

# What is Spring Boot Actuator?
->Spring Boot Actuator is a feature used to monitor and check the health of a Spring Boot application. It provides different endpoints that show information about the application, such as whether the application is running, its health status, and application metrics. For example, the /actuator/health endpoint can be used to check whether the application is working properly. It is mainly used for monitoring and managing applications in production.

# What is application.properties in Spring Boot?
->application.properties is a configuration file in a Spring Boot application. We use it to store application settings such as the server port, database connection details, username, password, and other configuration values. Spring Boot reads these properties when the application starts. For example, we can use server.port=8081 to change the default server port from 8080 to 8081.

# What is application.yml in Spring Boot?
-> application.yml is another configuration file used in a Spring Boot application. It is used to store settings such as the server port, database details, and other application configurations. It uses YAML format, which allows us to write related settings in a clear and structured way. application.properties and application.yml are mainly used for the same purpose, but their format is different.

# What is the difference between application.properties and application.yml?
->Both application.properties and application.yml are used to store configuration settings in a Spring Boot application. The main difference is their format. application.properties uses key-value pairs, while application.yml uses YAML format with indentation. Both can be used for settings like server port, database connection, and application configuration. We can choose either one based on our project requirement.

# What is @Bean in Spring Boot?
->@Bean is an annotation used to tell Spring to create and manage an object as a Spring Bean. We normally use it on a method inside a @Configuration class. The object returned by that method is managed by Spring and can be injected into other classes. We use @Bean when we want to create and configure an object ourselves, especially when the class is from a third-party library and we cannot add @Component to it.

# What is @Configuration in Spring Boot?
->@Configuration is an annotation used to tell Spring that a class contains configuration settings for the application. It is mainly used to define Spring Beans using the @Bean annotation. Spring reads this class and creates the required objects as Beans. For example, if we create a method with @Bean inside a @Configuration class, Spring creates and manages the object returned by that method.

# What is Dependency Injection, and what are its types in Spring Boot?
->Dependency Injection means Spring provides the required object to a class instead of the class creating the object itself. It helps us reduce the dependency between classes and makes the code easier to manage and test. There are mainly three types of Dependency Injection in Spring: constructor injection, setter injection, and field injection. Constructor injection is generally preferred because the required dependency is provided when the object is created.

# What is Constructor Injection in Spring Boot?
->Constructor Injection is a type of Dependency Injection where Spring provides the required dependency through the class constructor. It is commonly preferred because the dependency is available when the object is created, and it makes the dependency clear and easier to test. We do not need to use @Autowired when the class has only one constructor.”

# What is Setter Injection in Spring Boot?
->Setter Injection is a type of Dependency Injection where Spring provides the required dependency through a setter method. We use a setter method to set the dependency after the object is created. It is useful when the dependency is optional or may need to be changed later. However, for required dependencies, constructor injection is generally preferred.”

# What is Field Injection in Spring Boot?
->Field Injection is a type of Dependency Injection where Spring directly injects the required dependency into a class field using the @Autowired annotation. It is easy to write, but it is generally not recommended because the dependency is not clearly shown through the constructor and it can make testing harder. Constructor Injection is usually preferred over Field Injection.”

# What is the Spring Bean Life Cycle?
->The Spring Bean life cycle is the process through which a Spring Bean is created, initialized, used, and finally destroyed. First, Spring creates the Bean object. Then Spring injects its required dependencies. After that, initialization methods are called and the Bean is ready to use. When the application is stopped, Spring calls the destroy method and removes the Bean. So, the main stages are Bean creation, dependency injection, initialization, usage, and destruction.

# What is @PostConstruct in Spring Boot?
-> @PostConstruct is an annotation used on a method that should run automatically after Spring creates the Bean and completes dependency injection. We can use it to perform initialization work, such as loading some data or setting initial values. The method marked with @PostConstruct runs only once during the Bean's creation.”

# What is @PreDestroy in Spring Boot?
->@PreDestroy is an annotation used on a method that should run automatically before Spring removes a Bean from the container. We use it to perform cleanup work, such as closing resources or connections.

# What is @Scope in Spring Boot?
->@Scope is used to define how Spring creates and manages a Bean. By default, Spring creates one object of a Bean for the entire application. We can change this behavior using @Scope. ("prototype") tells Spring to create a new object each time the Bean is requested.”

# What is Singleton and Prototype scope in Spring Boot?
->Singleton and Prototype are two Spring Bean scopes. In Singleton scope, Spring creates only one object of a Bean and uses the same object whenever it is requested. Singleton is the default scope in Spring. In Prototype scope, Spring creates a new object every time the Bean is requested. So, Singleton means one Bean object is shared, while Prototype means a new Bean object is created each time.”

# What is the difference between @Autowired and Constructor Injection?
->@Autowired is used to tell Spring to inject a required dependency. Constructor Injection is a way of injecting that dependency through the constructor. Constructor Injection is generally preferred because it makes required dependencies clear and makes the class easier to test.”

# What is @Qualifier in Spring Boot?
->@Qualifier is used when we have multiple Beans of the same type and Spring does not know which Bean to inject. It tells Spring exactly which Bean we want to use. We usually use @Qualifier along with @Autowired or constructor injection. For example, if we have two payment service Beans, @Qualifier can tell Spring which payment service should be injected.


# What is @Primary in Spring Boot?
->@Primary is used when we have multiple Beans of the same type and Spring needs to choose one Bean by default. We can mark one Bean with @Primary, and Spring will use that Bean when no specific Bean is selected. If we use @Qualifier, we can select a different Bean instead.


# What is @Value in Spring Boot?
->@Value is used to read values from the configuration file, such as application.properties or application.yml, and use them inside a Java class. It is useful when we want to keep values like application name, server settings, or other configuration values outside the Java code. Spring reads the value from the configuration file and gives it to the variable.

# What is @Profile in Spring Boot?
->@Profile is used to create different configurations for different environments, such as development, testing, and production. It allows us to load specific Beans or configurations only for a particular environment. For example, we can have one database configuration for development and another for production. We can activate a profile using the spring.profiles.active property.

# What is @Transactional in Spring Boot?
->@Transactional is used to manage database transactions. It makes sure that multiple database operations are completed as one unit. If all operations are successful, the changes are saved in the database. If an error occurs, the changes can be rolled back. It is commonly used in the service layer when a method performs multiple database operations.”

# What is Spring Boot Starter Dependency?
->Spring Boot Starter Dependency is a dependency that contains the required libraries for a specific feature. Instead of adding each library separately, we can add one starter dependency. For example, spring-boot-starter-web provides the libraries required to create web applications and REST APIs. spring-boot-starter-data-jpa provides the libraries required to work with JPA and databases. Starters make it easier to add the required dependencies to a Spring Boot project.”

# What is Spring Boot Starter Web?
->spring-boot-starter-web is a Spring Boot dependency used to create web applications and REST APIs. It provides the required libraries for Spring MVC, REST API development, and an embedded Tomcat server. When we add this dependency, we can use annotations such as @RestController, @GetMapping, @PostMapping, and @RequestBody to create REST APIs.”


# What is spring-boot-starter-data-jpa?
->spring-boot-starter-data-jpa is a Spring Boot dependency used to work with databases using JPA. It provides the required libraries for JPA and Hibernate. It helps us perform database operations such as saving, finding, updating, and deleting data without writing a lot of SQL code. We can use interfaces like JpaRepository to perform these operations easily.”

# What is JpaRepository in Spring Boot?
->JpaRepository is an interface provided by Spring Data JPA. It is used to perform database operations without writing the common SQL queries manually. It provides methods like save(), findById(), findAll(), deleteById(), and existsById(). We create our repository interface by extending JpaRepository and provide the Entity class and the type of its primary key.”

# What is the difference between JpaRepository, CrudRepository, and Repository?
->Repository is a marker interface that is used as the base for Spring Data repository interfaces. CrudRepository provides basic database operations such as save, find, update, and delete. JpaRepository provides all the operations of CrudRepository and also provides additional features for JPA, such as pagination and sorting. So, JpaRepository has more features than CrudRepository, while Repository mainly acts as a base interface.”

# What is an Entity in Spring Boot?
->An Entity is a Java class that represents a table in the database. We use the @Entity annotation to tell JPA that the class should be mapped to a database table. Each object of the Entity represents a row in the table, and its fields represent the columns. We usually use @Id to define the primary key of the Entity.

# What is @Entity and @Id in Spring Boot?
->@Entity is used to tell JPA that a Java class should be mapped to a database table. Each object of that class represents a row in the table. @Id is used to identify the primary key of the table. Every Entity must have an @Id field that uniquely identifies each record.”

# What is @GeneratedValue in Spring Boot?
->@GeneratedValue is used with @Id to automatically generate the primary key value for an Entity. It means we do not need to manually provide the ID when creating a new record. JPA can generate the ID automatically using strategies such as IDENTITY, SEQUENCE, and AUTO. For example, when we save a new employee, the database can automatically generate an ID like 1, 2, 3, and so on.”

# What is Hibernate in Spring Boot?
->Hibernate is an ORM framework used to connect Java applications with databases. ORM stands for Object Relational Mapping. It maps Java classes to database tables and Java objects to database records. Hibernate helps us perform database operations without writing SQL queries for every operation. Spring Data JPA commonly uses Hibernate as its default JPA implementation.”

# What is JPA in Spring Boot?
->JPA stands for Java Persistence API. It is a specification used to manage data between a Java application and a database. JPA provides annotations such as @Entity, @Id, and @GeneratedValue to map Java classes and fields to database tables and columns. JPA itself is not an implementation. Hibernate is one of the implementations of JPA. In Spring Boot, we commonly use Spring Data JPA with Hibernate to perform database operations.

# What is the difference between JPA and Hibernate?
->JPA is a specification that defines rules for working with databases in Java applications. Hibernate is a framework that implements those JPA rules. JPA tells us what features should be provided, while Hibernate provides the actual implementation. In Spring Boot, we commonly use Spring Data JPA, and Hibernate works in the background to perform the database operations.”

# What is Spring Data JPA?
->Spring Data JPA is a part of the Spring framework that makes it easier to work with databases using JPA. It provides ready-made interfaces like JpaRepository, which give us methods for common database operations such as save, find, update, and delete. It reduces the amount of database code we need to write. Spring Data JPA uses JPA, and Hibernate commonly works in the background to perform the actual database operations.”

# What is the difference between save() and saveAndFlush() in JPA?
->save() is used to save an entity to the database, but the actual SQL operation may not happen immediately. It can wait until the transaction is committed .saveAndFlush() saves the entity and immediately flushes the changes to the database. We use saveAndFlush() when we need the changes to be sent to the database immediately.

# What is a Derived Query Method in Spring Data JPA?
->A Derived Query Method is a method in a repository where Spring Data JPA creates the database query automatically based on the method name. We don't need to write the SQL query manually. For example, findByName(String name) tells Spring to find an employee whose name matches the given name. We can also use methods like findBySalaryGreaterThan() or findByDepartment(). This makes it easy to create common database queries.”

# What is a Custom Query in Spring Data JPA?
->A Custom Query is a query that we write ourselves when the required database operation cannot be easily done using a derived query method. We can use the @Query annotation to write a JPQL or native SQL query inside the repository. For example, we can use @Query("SELECT e FROM Employee e WHERE e.salary > :salary") to find employees whose salary is greater than a given value. It gives us more control over the database query.”

# What is JPQL in Spring Data JPA?
->JPQL stands for Java Persistence Query Language. It is a query language used to query Entity objects in JPA. Unlike SQL, JPQL works with Java Entity classes and their fields instead of database tables and columns. For example, we can write a JPQL query to find employees whose salary is greater than a particular amount. JPQL is database-independent, so the same query can work with different databases.”

# What is Native Query in Spring Data JPA?
->A Native Query is a query written using the actual SQL syntax of the database. We use the nativeQuery = true option with the @Query annotation. Unlike JPQL, which uses Entity classes and their fields, a Native Query uses the actual database table and column names. We use Native Queries when we need database-specific SQL or when a query is difficult to write using JPQL.”

# What is Exception Handling in Spring Boot?
->Exception Handling is used to handle errors that occur while running a Spring Boot application. Instead of showing an error or technical message directly to the client, we can handle the exception and return a proper response with an appropriate HTTP status and message. In Spring Boot, we commonly use @ExceptionHandler to handle exceptions in a controller.

# What is @ExceptionHandler in Spring Boot?
->@ExceptionHandler is used to handle a specific exception in a controller. When that exception occurs, Spring calls the method marked with @ExceptionHandler and returns a proper response to the client. For example, we can use it to handle NullPointerException, ResourceNotFoundException, or other application-specific exceptions. It helps us return a meaningful error message instead of showing an internal server error.”

# What is @ControllerAdvice in Spring Boot?
->@ControllerAdvice is used to handle exceptions globally in a Spring Boot application. It allows us to write exception-handling code in one class instead of writing it separately in every controller. We can use @ExceptionHandler methods inside @ControllerAdvice to handle different exceptions. This helps us keep the code clean and return a common error response to the client.”

# What is the difference between @ControllerAdvice and @RestControllerAdvice?
->@ControllerAdvice is used to handle exceptions globally for controllers. When we use it with @ResponseBody, it can return data such as JSON. @RestControllerAdvice is a combination of @ControllerAdvice and @ResponseBody, so it directly returns the response data to the client. For REST APIs, we usually use @RestControllerAdvice for global exception handling.”

# What is the difference between @ExceptionHandler and @ControllerAdvice?
->@ExceptionHandler is used to handle a specific exception. It is normally used inside a controller or advice class. @ControllerAdvice is used to handle exceptions globally for multiple controllers in one place. So, @ExceptionHandler handles the exception, while @ControllerAdvice helps us apply exception handling to the whole application.”

# What is ResponseEntity in Spring Boot?
->ResponseEntity is a class used to control the complete HTTP response from a REST API. It allows us to return the response body, HTTP status code, and HTTP headers. For example, after successfully creating an employee, we can return the employee data with a 201 Created status. It is useful when we want more control over the response sent to the client.”


# What is @Valid in Spring Boot?
->@Valid is used for validating the data received from the client. We use it with validation annotations such as @NotNull, @NotBlank, @Size, @Email, and @Min. When the client sends invalid data, Spring automatically checks the validation rules and can return an error response. It is commonly used with @RequestBody when receiving data through REST APIs.”

# What is DTO in Spring Boot?
->DTO is a Data Transfer Object used to transfer only the required data between the client and application layers. It helps separate the API data from the database Entity and improves security and maintainability

# What is the difference between Entity and DTO in Spring Boot?
->An Entity is a Java class that is directly connected to a database table. It is used to store and retrieve data from the database. A DTO is a Java class used to transfer data between the client and the application. We use DTOs to send only the required data to the client instead of exposing the complete Entity.

# What is the difference between @RequestBody and @ResponseBody?
->@RequestBody is used to get data from the client and convert the JSON data into a Java object. @ResponseBody is used to send the Java object or other data from the server back to the client, usually in JSON format. So, @RequestBody is used for data coming from the client to the server, and @ResponseBody is used for data going from the server to the client.

# What is the difference between PUT and PATCH in REST API?
->PUT is generally used to update the complete data of an existing resource, while PATCH is used to update only specific fields of an existing resource. 

# What is the difference between @RestController and @RestControllerAdvice?
->@RestController is used to create REST API controllers that handle client requests and return responses. @RestControllerAdvice is used to handle exceptions globally for all REST controllers. So, @RestController is mainly used for handling API requests, while @RestControllerAdvice is mainly used for common exception handling.”

# What is CORS in Spring Boot?
->CORS stands for Cross-Origin Resource Sharing. It is a security feature that controls whether a frontend application from one origin can access APIs from another origin. For example, if our React application runs on one port and our Spring Boot application runs on another port, the browser may block the request because they are different origins. We can configure CORS in Spring Boot to allow the required frontend origin to access our APIs.”


# What is Spring Security in Spring Boot?
->Spring Security is a framework used to secure Spring Boot applications. It provides features like authentication and authorization. Authentication checks whether the user is valid, and authorization checks what the user is allowed to access. We can use Spring Security to protect REST APIs, handle login, manage user roles and permissions, and secure application resources.

# What is Authentication and Authorization in Spring Security?
->Authentication means checking whether the user is valid or not. For example, when a user logs in with a username and password, the application checks whether the details are correct. Authorization means checking what the authenticated user is allowed to do. For example, an admin may be allowed to delete users, while a normal user may not have that permission. So, authentication is about who the user is, and authorization is about what the user can do.”

# What is JWT in Spring Boot?
->JWT stands for JSON Web Token. It is commonly used for authentication in REST APIs. When a user successfully logs in, the server creates a JWT token and sends it to the client. The client sends this token with future requests. The server checks the token to verify the user and allows access to protected APIs. JWT is useful because the server does not need to store the user's login session.”

# How does JWT authentication work in Spring Boot?
->First, the user sends their username and password to the login API. The server checks the user details. If the details are correct, the server creates a JWT token and sends it to the client. The client stores the token and sends it with every request to a protected API, usually in the Authorization header. Spring Security checks the token. If the token is valid, the user can access the API. If the token is invalid or expired, the server rejects the request.”

# What is the difference between Stateless and Stateful Authentication?
->In Stateful Authentication, the server stores information about the user's session. The server uses this session information to identify the user for future requests. In Stateless Authentication, the server does not store the user's session information. Instead, the client sends all required authentication information with each request, such as a JWT token. JWT-based authentication in Spring Boot is commonly stateless because the server verifies the token with each request.”

# What is Spring Boot Starter Security?
->spring-boot-starter-security is a dependency used to add Spring Security to a Spring Boot application. It provides the required libraries to implement security features such as authentication and authorization. After adding it, we can configure login, protect APIs, manage user roles and permissions, and use JWT-based security.”

# What is the difference between Authentication and Authorization in Spring Security?
->Authentication is used to verify the identity of a user. It checks whether the username and password or other login details are correct. Authorization is used to check what the authenticated user is allowed to access or do. For example, an admin can delete an employee, but a normal user may only view employee details. So, authentication checks who the user is, and authorization checks what the user can do.

# What is SecurityFilterChain in Spring Boot?
->SecurityFilterChain is used to configure the security rules of a Spring Boot application. It defines which APIs are public and which APIs require authentication. We can also use it to configure login, logout, roles, permissions, CSRF, and other security settings. In modern Spring Security, we usually define a SecurityFilterChain as a @Bean to configure application security.”

# What is PasswordEncoder in Spring Security?
->PasswordEncoder is used to securely store and check user passwords. We should not store passwords as plain text in the database. PasswordEncoder converts the password into a secure encoded form before storing it. When the user logs in, it checks the entered password against the stored encoded password. A commonly used implementation is BCryptPasswordEncoder.”

# What is UserDetailsService in Spring Security?
->UserDetailsService is an interface provided by Spring Security. It is used to load user information from a database or another source during authentication. We implement the loadUserByUsername() method to find the user and return the user's details, such as username, password, and roles. Spring Security then uses this information to verify the user during login.”

# What is UserDetails in Spring Security?
->UserDetails is an interface in Spring Security that contains information about a user. It provides details such as username, password, and user authorities or roles. When a user logs in, Spring Security uses UserDetails to get the user's information and check whether the user is authenticated and what permissions the user has.”

# What is the difference between UserDetailsService and UserDetails?
->UserDetailsService is used to load user information, usually from a database. It provides the loadUserByUsername() method to find a user. UserDetails is used to store the user's information, such as username, password, and roles. So, UserDetailsService finds the user, and UserDetails contains the user's details.”


# What is SecurityContext in Spring Security?
->SecurityContext is used by Spring Security to store information about the currently authenticated user. After successful authentication, Spring Security stores the user's authentication details in the SecurityContext. We can use it to get information about the logged-in user, such as the username and roles, during a request.”

# What is Authentication object in Spring Security?
->The Authentication object contains information about the currently logged-in user. It contains details such as the username, password, and authorities or roles of the user. After successful authentication, Spring Security stores this object in the SecurityContext. We can use the Authentication object to get information about the logged-in user and check their roles or permissions.”

# What is the difference between Authentication and SecurityContext in Spring Security?
->Authentication is an object that contains information about the currently authenticated user, such as username and roles. SecurityContext is used to store the Authentication object for the current request. So, Authentication contains the user information, while SecurityContext stores that authentication information.”

# What is a Filter in Spring Boot?
->A Filter is used to process HTTP requests and responses before they reach the controller or before the response is sent back to the client. Filters are commonly used for tasks such as checking authentication, logging requests, adding headers, and checking tokens. In JWT authentication, a filter can read the JWT token from the request, validate it, and set the authenticated user in the SecurityContext.”


# What is AOP in Spring Boot?
->AOP stands for Aspect-Oriented Programming. It is used to handle common tasks that are needed in multiple parts of an application, such as logging, security, transaction management, and exception handling. In Spring Boot, AOP allows us to separate these common tasks from the main business logic, which makes the code cleaner and easier to maintain.”

# What are the main annotations used in Spring AOP?
->The main annotations used in Spring AOP are @Aspect, @Before, @After, @AfterReturning, @AfterThrowing, and @Around. @Aspect defines an AOP class. @Before runs before a method, @After runs after a method, and @Around can run code before and after the method. These annotations are commonly used for logging, security, and transaction-related tasks.”

# What is the difference between @Before, @After, and @Around in Spring AOP?
->@Before runs before the target method executes. @After runs after the target method finishes, whether it succeeds or throws an exception. @Around gives complete control over the method execution, so we can run code before and after the method and also decide whether the method should execute.”

# What is the difference between @OneToMany and @ManyToOne in JPA?

“@OneToMany means one entity can have multiple related entities. For example, one department can have many employees. @ManyToOne means many entities can belong to one entity. For example, many employees can belong to one department. These annotations are used to define relationships between entities in JPA.”

# What is the difference between @OneToOne and @OneToMany in JPA?

“@OneToOne means one entity is related to only one entity. For example, one employee has one employee ID card. @OneToMany means one entity can be related to multiple entities. For example, one department can have many employees.”

# What is @ManyToMany in JPA?

“@ManyToMany is used when many records of one entity can be related to many records of another entity. For example, one student can enroll in many courses, and one course can have many students. JPA usually manages this relationship using a separate join table.”

# What is Lazy Loading and Eager Loading in JPA?
->Lazy Loading means related data is loaded only when we actually need it. Eager Loading means related data is loaded immediately along with the main entity. Lazy Loading can improve performance because it avoids loading unnecessary data. In JPA, @OneToMany and @ManyToMany use Lazy Loading by default, while @ManyToOne and @OneToOne use Eager Loading by default.”

# What is Cascade Type in JPA?
->Cascade Type defines how operations performed on a parent entity should be applied to its related child entities. For example, if we save or delete a parent entity, the same operation can be automatically applied to its child entities. Common cascade types are PERSIST, MERGE, REMOVE, REFRESH, and ALL.”

# What is Orphan Removal in JPA?
->Orphan Removal is used to automatically delete a child entity when it is removed from the parent entity’s relationship. For example, if an order has multiple order items and we remove one item from the order, orphanRemoval = true can automatically delete that item from the database.”

# What is the Entity Lifecycle in JPA?
->The Entity Lifecycle describes the different states of an entity in JPA. The main states are Transient, Persistent, Detached, and Removed. Transient means the object is newly created and not managed by JPA. Persistent means the entity is managed by the persistence context. Detached means it was managed before but is no longer managed. Removed means the entity is marked for deletion from the database.”

# What is Dirty Checking in Hibernate?
->Dirty Checking is a feature of Hibernate that automatically detects changes made to a managed entity. When the transaction is committed, Hibernate compares the current entity with its original state and automatically generates an UPDATE query if there are changes. We do not need to call update() manually.

# What is the N+1 Query Problem in Hibernate?
->The N+1 Query Problem happens when Hibernate executes one query to get the main records and then executes an additional query for each related record. For example, one query gets 10 departments, and then Hibernate executes 10 more queries to get employees for each department. This can reduce application performance. We can solve it using techniques like JOIN FETCH, entity graphs, or batch fetching.”

# What is the difference between save() and persist() in JPA?
->save() is a method provided by Spring Data JPA, usually through JpaRepository, and it can be used to insert or update an entity. persist() is a method of the JPA EntityManager and is mainly used to make a new entity persistent. persist() is used for new entities, while save() can handle both new and existing entities.”

# What is the difference between findById() and getReferenceById() in JPA?
->findById() immediately checks the database and returns an Optional containing the entity if it exists. getReferenceById() returns a reference or proxy to the entity without immediately loading it from the database. The database may be accessed later when we use the entity. findById() is commonly used when we need to check whether the record exists and get its data.”

# What is the difference between flush() and save() in JPA?
->save() is used to save an entity to the database through Spring Data JPA. flush() forces Hibernate to synchronize the changes in the persistence context with the database immediately. save() does not always execute the SQL query immediately, while flush() sends the pending changes to the database.”


# What is the difference between @Transactional and @Commit in Spring?
->@Transactional is used to manage a database transaction. All database operations inside the method are treated as one transaction. If an error occurs, the transaction can be rolled back. @Commit is mainly used in testing to commit a test transaction. In normal application code, we usually use @Transactional rather than @Commit.”

# What are Transaction Propagation levels in Spring?
->Transaction Propagation defines how a method should behave when it is called inside an existing transaction. The most commonly used type is REQUIRED, which joins the existing transaction or creates a new one if no transaction exists. Other propagation types include REQUIRES_NEW, SUPPORTS, MANDATORY, NOT_SUPPORTED, NEVER, and NESTED.”


# What is Rollback in Spring Transactions?
->Rollback means undoing all database changes made during a transaction when an error occurs. In Spring, @Transactional automatically rolls back a transaction when an unchecked exception occurs by default. This helps keep the database in a consistent state.”

# What is readOnly in @Transactional?
->readOnly = true is used when a transaction is only for reading data and we do not want to modify the database. It can help the database and Hibernate optimize the transaction. For example, we can use @Transactional(readOnly = true) for a method that only fetches employee records.”

# What is the difference between REQUIRED and REQUIRES_NEW propagation?
->REQUIRED joins the existing transaction if one is available. If there is no existing transaction, it creates a new transaction. REQUIRES_NEW always creates a new transaction and suspends the existing transaction. So, REQUIRED shares the current transaction, while REQUIRES_NEW uses a separate transaction.”

# What is the difference between @Transactional and programmatic transaction management?
->@Transactional is declarative transaction management. We simply add the annotation, and Spring manages the transaction automatically. Programmatic transaction management means we manually control the transaction using classes like TransactionTemplate or PlatformTransactionManager. @Transactional is preferred in most applications because it requires less code and is easier to maintain.”

# What is the difference between @Transactional on a class and on a method?
->When @Transactional is placed on a class, it applies to all public methods of that class by default. When it is placed on a method, it applies only to that specific method. If both are present, the method-level @Transactional takes priority over the class-level configuration.”

# What is @Async in Spring Boot?
->@Async is used to run a method asynchronously in a separate thread. It allows the calling method to continue without waiting for the method to finish. To use @Async, we usually enable asynchronous processing using @EnableAsync. It is useful for tasks like sending emails, notifications, or processing background tasks.”


# What is @Scheduled in Spring Boot?
->@Scheduled is used to run a method automatically at a fixed time or at a fixed interval. We need to enable scheduling using @EnableScheduling. It is commonly used for tasks like sending daily reports, deleting old data, or running regular background jobs.”

# What is the difference between @Async and @Scheduled in Spring Boot?
->@Async is used to run a method asynchronously in a separate thread when the method is called. @Scheduled is used to run a method automatically at a specific time or at a fixed interval. For example, @Async can be used for sending an email in the background, while @Scheduled can be used to run a daily report automatically.”

# What is the difference between @Filter, @Interceptor, and @Aspect in Spring Boot?
->A Filter works at the servlet level and processes requests before they reach the Spring application. An Interceptor works at the Spring MVC level and can run before or after a controller method. An Aspect works at the method level and is mainly used for cross-cutting concerns like logging, security, and transactions. So, Filter is for HTTP requests, Interceptor is for controller processing, and Aspect is for method-level operations.”

# What is Circular Dependency in Spring?
->Circular dependency happens when two or more Spring beans depend on each other. For example, ServiceA depends on ServiceB, and ServiceB also depends on ServiceA. This creates a dependency cycle and can cause bean creation problems. Constructor injection can make such problems easier to detect and avoid.”

# What is @Lazy in Spring Boot?
->@Lazy is used to delay the creation of a Spring Bean until it is actually needed. By default, Spring creates singleton beans when the application starts. When we use @Lazy, the bean is created only when it is first requested. It can help reduce application startup time when a bean is expensive to create.”

# What is the difference between @Lazy and @Scope("prototype") in Spring?
->@Lazy controls when a bean is created. The bean is created only when it is first needed. prototype scope controls how many instances of a bean are created. A new instance is created each time the bean is requested. So, @Lazy is about creation time, while prototype scope is about bean instances.”

# What is @EnableAsync in Spring Boot?
->@EnableAsync enables asynchronous processing in a Spring Boot application. It allows us to use the @Async annotation on methods. When an @Async method is called, Spring runs it in a separate thread instead of making the caller wait for it to finish.”

# What is @EnableScheduling in Spring Boot?
->@EnableScheduling enables scheduled task execution in a Spring Boot application. It allows us to use the @Scheduled annotation on methods. After enabling it, Spring automatically runs the scheduled methods according to the configured time or interval.”

# What is @EnableMethodSecurity in Spring Security?
->@EnableMethodSecurity enables method-level security in a Spring Boot application. It allows us to use annotations like @PreAuthorize and @PostAuthorize to control access to specific methods. For example, we can allow only users with the ADMIN role to call a particular service method.”

# What is the difference between hasRole() and hasAuthority() in Spring Security?
->hasRole() is mainly used to check a user’s role, such as ADMIN or USER. Spring Security normally adds the ROLE_ prefix to roles. hasAuthority() checks the exact authority name stored for the user. For example, we can use hasRole('ADMIN') for a role and hasAuthority('READ_USERS') for a specific permission.”

# What is Role-Based Authorization in Spring Security?
->Role-Based Authorization means giving different access to users based on their roles. For example, an ADMIN can create, update, and delete users, while a normal USER can only view users. In Spring Security, we can implement role-based authorization using hasRole(), hasAuthority(), or @PreAuthorize.”

# What is Session Management in Spring Security?
->Session Management controls how user sessions are handled after authentication. It can control the number of sessions a user can have and what happens when a new login occurs. In JWT-based authentication, we usually use stateless session management because the server does not store the user’s login session.”

# What is Stateless Authentication in Spring Security?
->Stateless Authentication means the server does not store the user’s authentication session. In JWT-based authentication, the client sends the JWT token with every request. The server validates the token and identifies the user from it. This makes the application easier to scale because the server does not need to maintain user sessions.”

# hat is OncePerRequestFilter in Spring Security?
->OncePerRequestFilter is a Spring class used to make sure a filter runs only once for each HTTP request. It is commonly used in JWT authentication. We can create a JWT filter by extending OncePerRequestFilter, read the token from the request, validate it, and set the authenticated user in the SecurityContext.”

# How does JWT Authentication work in Spring Security?
->First, the user sends their username and password to the login API. Spring Security verifies the credentials. If they are correct, the server creates a JWT token and sends it to the client. The client sends this token with every protected request in the Authorization header. The JWT filter reads and validates the token, gets the user information, and sets the authentication in the SecurityContext. Then Spring Security allows the request to access the protected resource.”

# What is Microservices Architecture?
->Microservices Architecture is an approach where a large application is divided into small, independent services. Each service handles a specific business function and can be developed, deployed, and scaled separately. For example, an e-commerce application can have separate services for users, products, orders, and payments. These services communicate with each other using REST APIs or other communication methods.”

# What are the advantages of Microservices Architecture?
->The main advantages of Microservices are independent development, independent deployment, easy scaling, better fault isolation, and flexibility in choosing technologies. Each service can be developed and deployed separately. If one service fails, other services can continue working, depending on how the system is designed.”

# What is the difference between Monolithic Architecture and Microservices Architecture?
->In Monolithic Architecture, the entire application is developed and deployed as one single application. In Microservices Architecture, the application is divided into multiple small and independent services. In a monolithic application, one change may require redeploying the whole application. In microservices, we can develop, deploy, and scale each service independently.”

# What is Service Discovery in Microservices?
->Service Discovery is used to help microservices find and communicate with each other without using fixed IP addresses or ports. Each service registers itself with a service registry, and other services can find its location from the registry. In Spring Cloud, Eureka is commonly used as a service discovery server.”

# What is an API Gateway in Microservices?
->An API Gateway is a single entry point for clients to access multiple microservices. It receives the client request and routes it to the correct service. It can also handle authentication, authorization, logging, rate limiting, and other common tasks. In Spring Cloud, we can use Spring Cloud Gateway to implement an API Gateway.”

# What is an API Gateway vs Service Discovery?
->API Gateway is the entry point for clients. It receives client requests and routes them to the correct microservice. Service Discovery helps microservices find the location of other microservices dynamically. For example, Spring Cloud Gateway can be used as an API Gateway, while Eureka can be used for Service Discovery.”

# What is an API Gateway in Spring Cloud?
->API Gateway is a single entry point for clients in a microservices application. It receives requests from the client and forwards them to the correct microservice. It can also handle authentication, authorization, logging, rate limiting, and routing. In Spring Cloud, we commonly use Spring Cloud Gateway to create an API Gateway.

# What is the difference between Synchronous and Asynchronous communication in Microservices?
->Synchronous communication means the calling service waits for a response from the other service before continuing. For example, Service A calls Service B using a REST API and waits for the response. Asynchronous communication means the calling service does not wait for an immediate response. It can send a message to a message broker like Kafka or RabbitMQ, and the other service processes it later.

# What is OpenFeign in Spring Cloud?
->OpenFeign is a declarative HTTP client used for communication between microservices. We create an interface and define the API methods, and Feign handles the HTTP communication for us. It reduces the amount of code needed to call another microservice. For example, an Order Service can use a Feign Client to call the User Service.”

# What is Circuit Breaker in Microservices?
->Circuit Breaker is a design pattern used to prevent repeated calls to a service that is failing. If a service fails multiple times, the Circuit Breaker temporarily stops sending requests to that service and returns a fallback response. After some time, it checks whether the service is working again. In Spring Boot, Resilience4j is commonly used to implement Circuit Breaker.”

# What is Config Server in Spring Cloud?
->Config Server is used to manage configuration settings for multiple microservices from one central location. Instead of keeping configuration separately in every service, we can store it in a central repository and let services get their configuration from the Config Server. This makes configuration management easier, especially when there are many microservices.”

# What is the difference between Config Server and application.properties?
->application.properties stores configuration inside a particular Spring Boot application. Config Server stores configuration centrally and allows multiple microservices to get their configuration from one place. So, application.properties is mainly local to one application, while Config Server is useful for managing configuration across multiple microservices.”

# What is the difference between Eureka Server and Eureka Client?
->Eureka Server acts as a service registry where microservices register themselves. Eureka Client is used by individual microservices to register with the Eureka Server and discover other services. For example, if the User Service and Order Service are Eureka Clients, they register with the Eureka Server, and the Order Service can find the User Service through Eureka.”

# What is Load Balancing in Microservices?
->Load Balancing means distributing incoming requests across multiple instances of a service. It helps prevent one service instance from receiving too many requests. In microservices, load balancing improves performance, availability, and reliability. Spring Cloud can provide load balancing using Spring Cloud LoadBalancer.”

# What is the difference between Client-Side and Server-Side Load Balancing?
->Client-Side Load Balancing means the client service chooses which service instance should receive the request. Server-Side Load Balancing means a separate load balancer receives the request and forwards it to one of the available service instances. In Spring Cloud, we commonly use Spring Cloud LoadBalancer for client-side load balancing.”

# What is Spring Cloud LoadBalancer?
->Spring Cloud LoadBalancer is a client-side load balancing solution used in microservices. It distributes requests among multiple instances of a service. It can work with service discovery tools like Eureka to find available service instances and choose one for the request.”

# What is the difference between REST API and Feign Client?
->REST API is an API that allows applications or microservices to communicate using HTTP methods like GET, POST, PUT, and DELETE. Feign Client is a tool used in Spring Cloud to call another microservice’s REST API easily. So, REST API provides the service, while Feign Client is one way to call that service.”

# What is Inter-Service Communication in Microservices?
->Inter-Service Communication means communication between two or more microservices. Microservices can communicate synchronously using REST APIs or OpenFeign, where one service waits for a response. They can also communicate asynchronously using message brokers like Kafka or RabbitMQ, where the services communicate through messages.”

# What is Fault Tolerance in Microservices?
->Fault Tolerance means making the application continue working even when one service fails. In microservices, we can use techniques like Circuit Breaker, Retry, Timeout, and Fallback. For example, if the Payment Service is temporarily down, the Order Service can return a proper fallback response instead of the whole application failing.”

 # What is Timeout in Microservices?
->Timeout means setting a maximum time for a service to wait for a response from another service. If the response does not come within that time, the request is stopped and an error or fallback response is returned. Timeout helps prevent the application from waiting too long when another service is slow or unavailable.”

# What is Fallback in Microservices?
->Fallback is a backup response or action used when a service is unavailable or fails. For example, if the Product Service is down, the application can return a message like ‘Product information is temporarily unavailable’ instead of failing completely. Fallback is commonly used with Circuit Breaker to improve fault tolerance.”

# What is Distributed Tracing in Microservices?
->Distributed Tracing is used to track a request as it moves through multiple microservices. For example, a request may go from the API Gateway to the Order Service, then to the Payment Service and Notification Service. Distributed tracing helps us find where a request failed or became slow. Tools like Zipkin and Jaeger can be used for distributed tracing.”

# What is Pagination in Spring Data JPA?
->Pagination is used to retrieve a large amount of data in smaller pages instead of fetching all records at once. In Spring Data JPA, we can use Pageable and Page for pagination. For example, instead of returning 10,000 employees at once, we can return 10 or 20 employees per page. This improves application performance and reduces the amount of data transferred.”


