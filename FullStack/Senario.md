# Your Spring Boot API was working fine earlier, but suddenly its response time increased from 200 ms to 8–10 seconds.
->First, I would check the application logs and monitoring metrics to find where the delay is happening. Then I would check the database queries, external API calls, CPU, memory, and thread or connection pools. If the database query is slow, I would optimize the query and add proper indexes. If an external service is causing the delay, I would check its response time and configure proper timeouts or circuit breakers. Finally, I would test the fix and monitor the API again.

# Your Spring Boot application is running, but suddenly users start getting “Database connection failed” errors. The application itself is healthy.

How would you investigate the issue and what would you do to fix it?

Answer:
First, I would check the application logs to identify the exact database error. Then I would verify whether the database server is running and reachable from the application. I would check the database URL, username, password, network connectivity, and connection pool configuration. I would also check whether the database has reached its maximum connection limit. After identifying the root cause, I would fix the configuration or database issue and verify the application again.

# A customer clicks the “Place Order” button twice because the first request takes a few seconds. Both requests reach your Spring Boot backend, and two orders are created.

How would you prevent duplicate orders?

Answer:
I would make the order creation operation idempotent. I would generate a unique request or idempotency key for each order attempt and store it in the database. Before creating an order, I would check whether that key has already been processed. I would also use a database unique constraint and transaction to make sure the same request cannot create multiple orders.

Idempotency means processing the same request multiple times should not create multiple effects. For example, if a user sends the same order request twice, only one order should be created.

# Your e-commerce application has only 1 laptop left in stock. Two users place an order at almost the same time. Both requests see the stock as 1, and both try to purchase it.

How would you prevent both users from successfully buying the same laptop?

Answer:
I would use a database transaction with locking. When one request checks and updates the stock, the product record is locked so another request cannot modify it at the same time. After the first transaction completes, the second request checks the updated stock and gets an out-of-stock response.

# Your Order Service calls a Payment Service. Suddenly, the Payment Service is down.

What will you do so that your Order Service does not also become slow or fail?

Answer:

“First, I will set a timeout so my service does not wait too long. Then I can use a circuit breaker like Resilience4j. If the Payment Service is down, the circuit breaker will stop sending requests for some time. I can also retry the request if it is a temporary problem. Finally, I can return a proper response to the user, such as ‘Payment service is temporarily unavailable.

# Your Spring Boot application is working fine, but after running for several hours, it becomes very slow and finally crashes with OutOfMemoryError.

What will you do?

Answer:

“First, I will check the application logs and memory usage. Then I will find which objects are using too much memory. I will check for memory leaks, large collections, and unnecessary objects. I will also check the cache and database data being loaded into memory. After fixing the main problem, I will test the application again and monitor its memory usage.

# Your Spring Boot API was working yesterday, but today users are getting 500 Internal Server Error. What will you check first?

Answer:

“First, I will check the application logs and find the exact exception. Then I will check the database, input data, and external services if the API depends on them. I will find the root cause and fix it. After fixing it, I will test the API again and check the logs to make sure the problem is solved.

# Your Spring Boot application was working normally, but suddenly all users are unable to log in. What will you check?

Answer:

“First, I will check the application logs for login-related errors. Then I will check the database connection and verify whether user data is available. I will also check the password, JWT, and Spring Security configuration. If the problem started after a recent change, I will check that change first. Then I will fix the root cause and test login again.

# Your application has 1,000 users. Suddenly, one user reports that they can see another user's order details.

How would you find and fix this problem?

Answer:

“First, I would check the API and security code. I would make sure the user ID is taken from the logged-in user's JWT, not directly trusted from the request. Then I would check the database query to make sure it returns only that user's data. I would also check authorization rules and test with different users. Finally, I would fix the issue and add proper security tests to prevent it from happening again.

# Your Spring Boot API works correctly for normal users, but admin users are getting 403 Forbidden when accessing the admin API.

What would you check and how would you fix it?

Answer:

“First, I will check the user's role in the JWT token. Then I will check the Spring Security configuration and make sure the admin API requires the correct role. I will also check whether I am using ROLE_ADMIN or ADMIN correctly. Finally, I will test the API with an admin user and confirm that the authorization works

# Your API is slow because a database query is taking 5 seconds. The table has millions of records.

What would you do to make the query faster?

Answer:

“First, I will check the SQL query and see why it is slow. Then I will check if the required columns have proper indexes. I will avoid fetching unnecessary data and use pagination for large results. I will also check the query execution plan. After making the changes, I will test the query again and compare the response time

# Suppose your order process does two things:

Creates an order in the database.
Reduces the product stock.

The order is created successfully, but stock update fails.

What will you do to make sure the data stays correct?

Answer:

“I will use a database transaction. Both operations should be part of the same transaction. If the stock update fails, the order creation should also be rolled back. This keeps the database consistent. In Spring Boot, I can use @Transactional for this.”

# Your Spring Boot application calls another service. Sometimes that service takes 30–40 seconds to respond, making your API very slow.

What would you do?

Answer:

“I will set a proper timeout for the external API call. I don't want my application to wait for a very long time. If the failure is temporary, I can retry the request. I can also use a circuit breaker like Resilience4j. If the service is still unavailable, I will return a proper response to the user.

# You have three microservices:

Order Service → Product Service → Database

The Product Service is down. Now users cannot place orders.

How would you design the system so that the Order Service can handle this situation properly?

Answer:

“I will use a timeout so the Order Service does not wait too long. I can use Resilience4j Circuit Breaker to stop repeated calls when the Product Service is down. I can also retry temporary failures. If the Product Service is still unavailable, I will return a proper error message or mark the order as pending, depending on the business requirement.”

# Your API returns a list of 100 orders. For each order, the application separately queries the customer details. The API becomes very slow.

What is the problem, and how would you fix it?

Answer:

“This can be an N+1 query problem. Instead of making a separate database query for every order, I would fetch the required data together using a proper join, fetch join, or optimized query. I would also check the Hibernate mappings and SQL generated by the application. This reduces the number of database queries and improves performance

This is an N+1 query problem. Since we are using JpaRepository, I would check the repository methods and the SQL queries generated by JPA. Instead of calling the repository separately for each order, I would create one optimized repository query using JOIN FETCH or a custom JPQL query to fetch the required data together. This reduces database calls and improves performance

# Your application has 1 million orders in the database. When the user opens the orders page, the API tries to return all orders and becomes very slow.

How would you solve this using Spring Data JPA?

Answer:

“I would use pagination instead of fetching all records at once. In Spring Data JPA, I can use Pageable with JpaRepository to fetch a limited number of records, such as 20 orders per page. This reduces database load and improves API response time.”

# A user updates their profile, but sometimes the changes are not saved in the database. There is no error shown to the user.

How would you investigate this issue in a Spring Boot application using JPA?

Answer:

“First, I would check the application logs and the service method. Then I would check whether the entity is actually being changed and whether the repository save operation is called. I would also check the transaction and database configuration. If the update is inside a transaction, I would check whether the transaction is being committed or rolled back. Finally, I would test the API and verify the data directly in the database.”

# Your Spring Boot application is working, but sometimes an API fails with a NullPointerException. How would you find the cause and fix it?

Answer:

“First, I would check the error logs and stack trace to find the exact line where the exception happened. Then I would check which object is null and why it was not initialized or returned. I would add proper null checks and validation where required. I would also handle cases where the database or request does not contain the expected data.”

# DELETE /api/users/10

A normal logged-in user sends a request to delete another user's account by changing the ID from 10 to 11.

How would you prevent this security problem?

Answer:

“I would not trust the user ID directly from the request. I would get the logged-in user's identity from the JWT token and check whether they have permission to delete that user. I would also configure Spring Security with proper roles and authorization rules. If the user does not have permission, I would return 403 Forbidden.


# A user sends this request to your Spring Boot API:

name = ""
email = "abc"
age = -5

The API should not accept this invalid data.

How would you handle validation in Spring Boot?

Answer:

“I would use Bean Validation in Spring Boot. I can use annotations like @NotBlank, @Email, and @Min in the DTO class. Then I would use @Valid in the controller to validate the request. If the data is invalid, Spring Boot will return a validation error instead of processing the request.


# Your Spring Boot application has many controllers. Different APIs are throwing exceptions, and each controller is handling them differently.

How would you create a common exception-handling system for the whole application?

Answer:

“I would use @ControllerAdvice with @ExceptionHandler. I can handle common exceptions in one class instead of writing the same exception-handling code in every controller. I would return a proper response with the HTTP status, error message, and timestamp. This makes the code cleaner and gives a consistent error response to the client.”

# Your Spring Boot application allows users to upload profile pictures. Suddenly, a user uploads a 500 MB file, which causes the application to use too much memory and become slow.

How would you handle this problem?

Answer:

“I would set a maximum file size in the application configuration. I would also validate the file type and reject files that are not allowed. For large files, I would avoid loading the complete file into memory. If we use cloud storage like Cloudinary or S3, I would upload the file there instead of storing large files directly in the application server

# Your product API is called thousands of times per minute, but the product data does not change very often. The database is getting too many requests.

How would you improve the performance?

Answer:

“I would use caching for frequently requested product data. For example, I can use Spring Cache with Redis. The first request gets the data from the database and stores it in the cache. The next requests can get the data from the cache instead of querying the database every time. When the product is updated, I would also update or clear the related cache.

# Two users edit the same product at almost the same time.

John changes the price from ₹1,000 → ₹1,200.
Mike changes the stock from 10 → 20.

Both save their changes, but one user's update overwrites the other user's changes.

How would you prevent this problem in Spring Boot + JPA?

Answer:

“I would use optimistic locking with JPA. I can add a @Version field to the entity. JPA checks the version before updating. If another user has already updated the record, the version will be different, and JPA will reject the second update. Then I can inform the user that the data was changed and ask them to refresh and try again.

# You deployed a new version of your Spring Boot application to production. After deployment, users start getting 500 errors, but the application worked correctly on your local machine.

What would you check first?

Answer:

“First, I would check the production application logs to find the exact error. Then I would check the environment variables, database configuration, application properties, and external service URLs. I would also check whether the correct JAR and configuration were deployed. After finding the root cause, I would fix it, redeploy, and test the API again.

# Your Spring Boot application has multiple transactions running at the same time. Suddenly, some database operations are stuck, and the database reports a deadlock.

What would you do to find and fix the problem?

Answer:

“First, I would check the database logs to find which transactions are causing the deadlock. Then I would check the order in which the application is accessing and updating tables. I would try to make all transactions access resources in the same order and keep transactions as short as possible. I would also check the database indexes and locking behavior. After making the changes, I would test the application with multiple requests again.

# Your API returns customer information along with thousands of records, and the response is very large. Users complain that the API is slow.

How would you improve it?

Answer:

“I would avoid returning unnecessary data. I would use pagination to return a limited number of records at a time. I would also return only the required fields using a DTO or projection. If the data is still large, I can use compression and caching where appropriate. This will reduce the response size and improve API performance.

# Your Spring Boot application takes 2–3 minutes to start in production, but it starts quickly on your local machine.

How would you investigate and fix this issue?

Answer:

“First, I would check the startup logs to see which part is taking the most time. I would check database connections, external service calls, entity scanning, and Spring configuration. I would also check whether the production environment has network or resource problems. After finding the slow component, I would optimize it and test the startup time again.”

# Your Spring Boot application suddenly starts showing:

HikariPool - Connection is not available

Users are getting database errors.

What could be the reason, and how would you fix it?

Answer:

“It means the application cannot get a free database connection. First, I would check if there are too many requests or long-running database queries. I would also check if transactions or database connections are staying open for too long. Then I would optimize the slow queries and transaction handling. If required, I would properly configure the Hikari connection pool size.


#  Your Spring Boot application normally handles 500 requests per minute, but suddenly it receives 10,000 requests per minute. The API becomes very slow.

What would you do to handle this situation?

Answer:

“First, I would check CPU, memory, database, and API response time to find the bottleneck. Then I would scale the application by running multiple instances behind a load balancer. I would also use caching for frequently requested data and optimize slow database queries. If some tasks are not required immediately, I can process them asynchronously

# Your Spring Boot API is returning HTTP 200 OK even when a user sends invalid data or requests a resource that does not exist.

How would you fix this?

Answer:

“I would return the correct HTTP status based on the situation. For invalid input, I would return 400 Bad Request. If the user is not authenticated, I would return 401 Unauthorized. If the user does not have permission, I would return 403 Forbidden. If the requested resource does not exist, I would return 404 Not Found. This makes the API easier for the frontend and other services to handle.

# You are using JpaRepository. One repository method is very slow:

findByCustomerIdAndStatus(...)

The database has millions of orders.

What would you check and how would you improve it?

Answer:

“First, I would check the SQL query generated by JPA and see how long it takes. Then I would check whether the columns used in the search have proper indexes. For this query, I would consider an index on customer_id and status. I would also make sure I am not fetching unnecessary data. After adding the index or optimizing the query, I would test the response time again.

# Your createOrder() method performs 3 operations:

Save the order
Reduce product stock
Save payment information

The first two operations succeed, but the payment operation fails.

What should happen to the first two operations, and how would you implement it in Spring Boot?

Answer:

“The first two operations should also be rolled back because the complete order process failed. I would put all three operations inside one transaction using @Transactional. If an exception occurs, the transaction will roll back the database changes, so the order and stock update will not remain.

# A user logs into your Spring Boot application successfully and gets a JWT token. But when they call a protected API, they receive 401 Unauthorized.

What would you check?

Answer:

“First, I would check whether the JWT token is being sent correctly in the Authorization header. Then I would check the token format, expiration time, secret key, and JWT validation code. I would also check whether the Spring Security filter is reading and validating the token correctly. After finding the problem, I would fix it and test the protected API again.”

# You have three microservices:

User Service
Order Service
Product Service

An interviewer asks:

“Should all three services use the same database, or should each service have its own database? Why?”

Answer:

“In a microservices architecture, ideally each service should have its own database. This keeps the services independent and prevents one service from directly depending on another service's database. Services communicate through APIs or messaging. This also makes it easier to scale and change each service independently.

# Your Order Service is running normally, but the Product Service suddenly goes down. Users are trying to place orders.

What should the Order Service do instead of continuously waiting for the Product Service?

Answer:

“I would set a timeout for the Product Service call. I would use a circuit breaker to stop repeated calls when the service is down. If the problem is temporary, I can retry the request. If the Product Service is still unavailable, I would return a proper error message or keep the order in a pending state, depending on the business requirement.

# A user reports that an API is failing in production, but you cannot reproduce the problem on your local machine.

How would you find what went wrong?

Answer:

“First, I would check the production logs. I would add useful logs around important operations, such as the request, user ID, database operation, and external service response. I would also log the exception and stack trace. I would avoid logging sensitive information like passwords or tokens. Using these logs, I can find where the problem happened and fix it.

# Your frontend sends a POST request to create an order. Because of a network problem, the frontend sends the same request again. Now two orders are created.

How would you make your API idempotent?

Answer:

“I would use a unique idempotency key for each order request. The backend would save that key with the order. If the same key comes again, I would check the database and return the existing order instead of creating a new one. This prevents duplicate orders.

# Your application is already running in production. You need to add a new column to the users table without breaking the existing application.

How would you safely make this database change?

Answer:

“First, I would create a proper database migration instead of changing the production database manually. I would add the new column in a backward-compatible way, so the old application can still work. Then I would deploy the new application version and start using the new column. I would test the migration in a staging environment before applying it to production.”

# Your mobile application is using an old version of an API:

GET /api/v1/users

Now you need to make major changes to the response, but you cannot break the existing mobile application.

How would you handle this?

Answer:

“I would create a new API version instead of changing the old API directly. For example, I can create /api/v2/users. The old mobile application can continue using v1, while new clients can use v2. After all clients move to v2, we can plan to remove v1.

# Two users try to withdraw money from the same bank account at exactly the same time. The account has ₹10,000, and both requests try to withdraw ₹8,000.

Both requests check the balance before either one updates it.

How would you prevent the account from going into an incorrect state?

Answer:

“I would use a database transaction with proper locking. When the first request checks and updates the balance, the account record is locked. The second request must wait. After the first transaction completes, the second request checks the updated balance. If there is not enough money, the second withdrawal will be rejected.

# Your Spring Boot API works correctly for small data, but when the database contains a large amount of data, the API becomes very slow and sometimes crashes.

What would you check first, and how would you fix it?

Answer:

“First, I would check the database query and see how much data it is fetching. I would use pagination instead of fetching all records. I would also check database indexes and optimize the query. If the API is returning too much data, I would use DTOs to return only the required fields. Then I would test the API with large data again.”

# Your Order Service calls a Payment Service. Normally it responds in 1 second, but sometimes it takes 20 seconds. This makes users wait for a long time.

How would you handle this in Spring Boot?

Answer:

“I would set a proper timeout for the Payment Service call. If the request fails because of a temporary problem, I can retry it. I would also use a circuit breaker like Resilience4j to stop repeated calls when the Payment Service is having problems. This prevents my Order Service from waiting for a long time.”

# Your Spring Boot application is deployed on a server, but it keeps restarting every few minutes.

How would you investigate this problem?

Answer:

“First, I would check the application logs to find why it is stopping. I would check for OutOfMemoryError, database connection problems, configuration errors, and unhandled exceptions. I would also check the server's CPU and memory usage. If the application is running in Docker, I would check the container logs and restart status. After finding the root cause, I would fix it and monitor the application.


# Your login API was working normally, but now login takes 5–8 seconds for every user.

You are using Spring Security + JWT + JPA.

How would you find the problem and fix it?

Answer:

“First, I would check the application logs and measure where the time is being spent. I would check the database query used to find the user and make sure the email or username column has an index. I would also check password verification and JWT generation. If the database query is slow, I would optimize it. Then I would test the login API again and check the response time.

# Your profile-picture upload works perfectly on your local machine, but after deploying your Spring Boot application to production, the upload fails with “File too large” or “Request rejected”.

What would you check?

Answer:

“First, I would check the Spring Boot file upload size configuration. Then I would check whether a reverse proxy like Nginx has its own request-size limit. I would also check the server and cloud configuration. After increasing the limit if required, I would test the upload again. I would still keep a reasonable maximum file size for security and performance.”

 # A customer places an order. Your system creates the order successfully, but the payment fails.

The customer sees “Payment Failed”, but the order is still marked as “Confirmed.”

How would you handle this situation?

Answer:

“I would not mark the order as confirmed until the payment is successful. I would keep the order in a status like PENDING_PAYMENT. If the payment fails, I would update the order to PAYMENT_FAILED. I would also use a transaction where possible and handle payment callbacks carefully so that the order and payment status always stay consistent.”

# Your Spring Boot application is running, but suddenly the MySQL database goes down.

Users are still sending requests to your APIs.

What should your application do, and how would you handle this situation?

Answer:

“First, I would check the database connection error in the logs. I would configure proper timeouts so requests do not wait forever. I would return a proper error response to the user instead of showing a technical error. I would also check the database health and connection pool. Once the database is available again, I would verify that the application reconnects correctly.”

# During a security review, you discover that user passwords are being stored directly in the database as plain text.

What would you do to fix this problem in a Spring Boot application?

Answer:

“I would never store passwords as plain text. I would use a password hashing algorithm such as BCrypt through Spring Security. When a user registers, I would hash the password before saving it. During login, I would compare the entered password with the stored hash. I would also make sure passwords are never written to logs or returned in API responses.”

# You deployed a new version of your Spring Boot application. Everything worked during testing, but after deployment, users report that an important feature is not working.

As a developer, what steps would you take to handle the issue?

Answer:

“First, I would check the production logs and identify the exact error. Then I would compare the production configuration with the testing environment. I would check the recent code changes, database changes, and external services. If the issue is serious, I would roll back to the previous working version. Then I would fix the problem, test it properly, and deploy the corrected version.

# our Spring Boot application works fine after starting, but after running for many hours, memory usage keeps increasing and the application eventually crashes.

How would you find the problem and fix it?

Answer:

“First, I would check the JVM memory usage and application logs. Then I would take a heap dump and find which objects are using too much memory. I would check for objects that are not being released, large collections, and incorrect caching. After fixing the memory leak, I would test the application for a longer time and monitor the memory again.

# Your application has a product search API:

GET /api/products/search?name=laptop

It works fast with 1,000 products, but becomes very slow when the database has 10 million products.

How would you improve this API?

Answer:

“First, I would check the database query and execution time. I would add a proper index for the search field and avoid fetching unnecessary columns. I would also use pagination so I don't return thousands of products at once. If the search requirement is more complex, I could use a search engine like Elasticsearch. Then I would test the API with a large amount of data.”

# Your Order Service crashes and restarts while processing an order. The user doesn't know whether the order was created or not.

When the user tries again, there is a possibility of creating a duplicate order.

How would you design the system to handle this situation?

Answer:

“I would use an idempotency key for the order request. The key would be stored in the database along with the order. If the service restarts and the same request comes again, I would check the key first. If the order was already created, I would return the existing order instead of creating a new one. This prevents duplicate orders even after a service failure.”

# Your Order Service crashes and restarts while processing an order. The user doesn't know whether the order was created or not.

When the user tries again, there is a possibility of creating a duplicate order.

How would you design the system to handle this situation?

Answer:

“I would use an idempotency key for the order request. The key would be stored in the database along with the order. If the service restarts and the same request comes again, I would check the key first. If the order was already created, I would return the existing order instead of creating a new one. This prevents duplicate orders even after a service failure.

# Your application was working correctly, but suddenly all protected APIs are returning 401 Unauthorized. Users can still access the login API.

You are using Spring Security + JWT.

What would you check first?

Answer:

“First, I would check if the JWT token is being sent correctly in the request. Then I would check the JWT secret key, token expiration, and JWT validation code. I would also check the Spring Security filter and make sure it is reading the token correctly. If the secret key or security configuration was recently changed, I would check that first.”


# Your Order Service shows that an order is “CONFIRMED”, but the Product Service shows that the product stock was not reduced.

Both services have their own databases.

How would you handle this problem in a microservices application?

Answer:

“Because each service has its own database, I would not use one normal database transaction across both services. I would use an event or message-based approach. For example, after the order is created, the Order Service can send an event to the Product Service to reduce the stock. If the stock update fails, we can retry the event or update the order status to failed or pending. This helps keep the data consistent between services.

# Your Spring Boot application is running in production, but suddenly CPU usage goes to 95–100% and the APIs become slow.

How would you investigate and fix the problem?

Answer:

“First, I would check the server and JVM CPU usage using monitoring tools. Then I would check which thread or process is using high CPU. I would check for infinite loops, heavy calculations, too many requests, or inefficient code. I would also check database queries and background jobs. After finding the main cause, I would fix the code or scale the application if more resources are needed.”

# Your Spring Boot application is receiving many requests. Suddenly, requests start waiting for a long time, even though CPU and memory usage are normal.

You discover that many threads are busy waiting for database or external API responses.

What would you check and how would you fix it?

Answer:

“First, I would check the thread pool and see how many threads are active and waiting. Then I would check slow database queries and external API calls. I would set proper timeouts so threads do not wait for too long. I would also optimize slow operations and configure the thread pool properly. If needed, I would move long-running tasks to asynchronous processing.”

# Your Spring Boot application works when you access it directly:

http://server:8080

But when users access it through Nginx, they get 502 Bad Gateway.

What would you check?

Answer:

“First, I would check whether the Spring Boot application is running and listening on the correct port. Then I would check the Nginx configuration and the proxy URL. I would also check whether Nginx can connect to the Spring Boot server. Finally, I would check both Nginx and Spring Boot logs to find the exact problem.”

# Your Spring Boot application is used by customers 24/7. You need to deploy a new version, but you cannot stop the application because users are continuously using it.

How would you deploy the new version without downtime?

Answer:

“I would run multiple instances of the application behind a load balancer. I would deploy the new version to one or more instances while the old version continues handling requests. After testing the new version, I would gradually send traffic to it. Once all traffic is moved, I can stop the old instances. This allows deployment without downtime

# Your login API is receiving thousands of requests from the same IP address in a short time. This could be a brute-force attack.

How would you protect the API?

Answer:

“I would add rate limiting to the login API. For example, I can allow only a limited number of login attempts from the same IP or account within a specific time. After too many failed attempts, I can temporarily block further requests. I would also log these attempts and monitor them for suspicious activity.”

# Your Spring Boot application receives the same Kafka message twice, and the order gets created twice. How would you handle this?

Answer:
I would make the Kafka consumer idempotent. I would store a unique message ID or event ID in the database. Before processing the message, I would check whether that ID was already processed. If it was already processed, I would skip it. This prevents duplicate orders even if Kafka delivers the same message more than once.

# Your Spring Boot application uses Redis for caching, but suddenly Redis goes down. What will you do?

Answer:
I would first check the logs and confirm that Redis is unavailable. The application should not completely fail because of the cache. I would handle the Redis exception and allow the application to fetch the data from the database. After Redis is restored, caching can work normally again.

# Your Spring Boot scheduled job runs every night, but in production it suddenly runs twice and creates duplicate records. How would you handle this?

Answer:
I would first check if multiple application instances are running, because each instance may execute the same scheduled job. I would use a distributed lock or a job scheduler so that only one instance runs the job at a time. I would also make the database operation idempotent to prevent duplicate records.

# Your React frontend is calling your Spring Boot API, but suddenly the browser shows a CORS error. What would you check?

Answer:
I would first check the browser error and confirm it is a CORS issue. Then I would check the Spring Boot CORS configuration and make sure the frontend URL, HTTP methods, and headers are allowed. I would also check whether the backend or proxy configuration was recently changed.

# Your Spring Boot application is working normally, but suddenly users start getting database connection errors. The logs show “Connection is not available”. What would you check?

Answer:
I would check if the connection pool is exhausted. I would look for long-running queries, transactions that are not completing, or connections that are not being released properly. Then I would fix the root cause and tune the connection pool if necessary.

# Your Spring Boot application has a login or search API, and you suspect it may be vulnerable to SQL injection. How would you handle it?

Answer:
I would avoid building SQL queries by directly joining user input. I would use prepared statements or JPA repository methods with parameters. I would also validate user input and test the API with different inputs to make sure SQL injection is not possible.

# Your Spring Boot application consumes Kafka messages, but suddenly messages are building up in the Kafka topic. The consumer is processing messages very slowly. What would you check?

Answer:
I would check the consumer logs and processing time. I would check if the database or any external API is slow. I would also check the consumer thread count and Kafka partition setup. If needed, I would increase consumers or optimize the slow processing logic.

# Your Spring Boot Kafka consumer crashes while processing a message. When it starts again, the same message is processed again. How would you handle this?

Answer:
I would make the consumer idempotent so processing the same message again does not create duplicate data. I would also use proper Kafka offset handling so the message is acknowledged only after successful processing. If processing fails, the message can be retried or sent to a Dead Letter Topic (DLT).

# Your product price is updated in the database, but the API is still showing the old price because Redis is returning cached data. How would you handle this?

Answer:
I would invalidate or update the Redis cache whenever the product price changes. This makes sure the next request gets the latest data from the database. For important data, I would also set a suitable cache expiration time.

# Your Spring Boot application works fine with 100 users, but when traffic increases to 10,000 users, the database becomes very slow. What would you do?

Answer:
I would first check slow queries, CPU, memory, and database connections. Then I would optimize queries and add proper indexes. I would use caching for frequently requested data and pagination for large results. If needed, I would also scale the database and application horizontally.

# Your Spring Boot application sometimes throws a database deadlock error when many users update orders at the same time. How would you solve it?

Answer:
I would check the database logs to find which transactions are causing the deadlock. I would make sure transactions access tables and rows in a consistent order and keep transactions short. I would also optimize queries and indexes, and add a retry mechanism for temporary deadlock failures.

# A user's JWT access token expires while they are using your application. You don't want them to log in again every few minutes. How would you handle this?

Answer:
I would use a refresh token. The access token will have a short expiry time, while the refresh token will have a longer expiry. When the access token expires, the client sends the refresh token to get a new access token without asking the user to log in again.

# Two users try to book the last available movie ticket at exactly the same time. Both requests see the ticket as available. How would you make sure only one user gets it?

Answer:
I would use a database transaction with locking. The first request locks the ticket record, checks availability, and books it. The second request waits for the lock and then sees that the ticket is already booked. This prevents double booking.

# You accidentally pushed a database password or AWS secret key to a public GitHub repository. What would you do immediately?

Answer:
I would revoke and rotate the exposed secret immediately. Then I would remove it from the repository history if necessary and check whether it was used by anyone. After that, I would store secrets in environment variables or a secret manager instead of putting them in GitHub.

# Your Spring Boot API works perfectly in Postman, but the React application gets an error when calling the same API from the browser. What would you check?

Answer:
I would first check the browser's Network tab and console to identify the error. Then I would check CORS configuration, request headers, HTTP method, URL, and authentication token. Since Postman works, I would mainly investigate browser-specific issues such as CORS or missing headers.

# An API performs three database operations. The first two succeed, but the third operation fails. After the API returns an error, you notice that the first two changes are still saved. How would you fix this?

Answer:
I would use a database transaction with @Transactional. All three operations should run inside the same transaction. If the third operation fails, the transaction should roll back, so the first two changes are also undone.

# Your Spring Boot application allows users to upload profile pictures to Cloudinary. The file upload succeeds locally, but in production Cloudinary returns an error. What would you check?

Answer:
I would check the production Cloudinary configuration, especially the cloud name, API key, and API secret. I would also check environment variables, network connectivity, file-size limits, and application logs. I would make sure the credentials are configured correctly without exposing them in the code.

# Your Order Service suddenly cannot find the Product Service, even though both services are running. You are using Eureka Service Discovery. What would you check?

Answer:
I would check whether both services are registered correctly with Eureka. Then I would check the service name, Eureka URL, network connectivity, and application configuration. I would also check the Eureka and Order Service logs to find the exact issue.

# Two developers modify the same Java file and push their changes to different Git branches. When you merge the branches, Git shows a merge conflict. What would you do?

Answer:
I would first understand both changes instead of blindly choosing one. I would resolve the conflict manually, test the application, and then commit the resolved changes. After that, I would push the updated branch and inform the team.

# Your Spring Boot application is running inside Docker, but the container keeps restarting again and again. What would you check?

Answer:
I would check the Docker logs first to find the error. Then I would check the application configuration, environment variables, database connection, port mapping, and memory usage. I would identify and fix the root cause instead of simply restarting the container.

# A normal user changes the userId in an API request and is able to access another user's profile. How would you fix this security issue?

Answer:
I would not trust the userId coming from the request. I would get the logged-in user's identity from the JWT token and verify that the user is allowed to access that data. I would also add proper authorization checks in the backend and return 403 Forbidden when access is not allowed.

# You deploy a new Spring Boot version that requires a new database column, but the database migration fails in production. What would you do?

Answer:
I would first check the migration logs and identify why it failed. I would avoid making random changes directly in production. I would fix and test the migration in a staging environment, take a database backup if required, and then run the corrected migration safely.

# Your Spring Boot application works fine after deployment, but after running for several hours, memory usage keeps increasing and eventually the application crashes. What would you check?

Answer:
I would check the JVM memory, garbage collection, and application logs. Then I would look for possible memory leaks such as large collections, static objects, caches, or resources that are not being released. I would use a heap dump to identify which objects are consuming too much memory and then fix the root cause.

# Your GET /products API sometimes returns duplicate products, even though the database does not contain duplicate records. How would you investigate this?

Answer:
I would first check the SQL query and any joins being used. A join can sometimes return the same product multiple times. I would check the generated SQL and database results, then fix the query or use DISTINCT if appropriate. I would also check whether the duplication is happening in the backend response or in the React frontend.

# Your Spring Boot application takes 2 minutes to start in production, but it starts in 10 seconds locally. How would you investigate this?

Answer:
I would check the Spring Boot startup logs to find which component is taking time. I would check database connections, external service calls, entity scanning, configuration, and network connectivity. I would identify the slow component and optimize or remove unnecessary startup operations.

# In your e-commerce application, Kafka sends these events for the same order: Order Created → Payment Success → Order Shipped. Sometimes they are processed in the wrong order. How would you make sure the events for the same order are processed in the correct order?

Answer:
I would use the order ID as the Kafka partition key. This makes events for the same order go to the same partition, where Kafka maintains their order. I would also make the consumer handle unexpected events safely.

# Your application is running, but users are getting errors because the database connection is down. The server itself is still responding. How would you make sure the system detects this problem automatically?

Answer:
I would use Spring Boot Actuator health checks. It can check dependencies like the database and show whether the application is healthy or not. I would connect these health checks to monitoring or a load balancer so unhealthy instances can be detected and removed from traffic.

# Your API receives a request containing a very large JSON payload, and the server's memory usage suddenly becomes very high. How would you handle this?

Answer:
I would set a maximum request size and reject requests that are too large. I would validate the input before processing it and avoid loading unnecessary data into memory. For very large data, I would use pagination or file/stream-based processing instead.


# A user forgets their password and requests a password reset. How would you design this securely?

Answer:
I would generate a random, short-lived reset token and send it to the user's registered email. The token should be stored securely and used only once. After the password is changed, I would invalidate the token and never expose the user's existing password.

# Two users are trying to buy the last product at the same time. Even though you use a transaction, both requests sometimes read the same stock value. What would you check?

Answer:
I would check the transaction isolation level and locking strategy. A transaction alone may not prevent concurrent reads and updates. For this case, I would use row-level locking, such as a pessimistic lock, so that one transaction updates the stock first and the other waits and then checks the latest value.

# Your request goes through API Gateway → Order Service → Payment Service → Notification Service, and the request fails somewhere. How would you find which service caused the problem?

Answer:
I would use distributed tracing and a unique correlation ID for each request. I would pass the ID between services and check the logs and traces using that ID. This helps me quickly identify which service failed and how long each service took.

# A customer clicks Pay twice because the first request appears stuck. The payment API receives both requests. How would you make sure the customer is not charged twice?

Answer:
I would use an idempotency key for each payment request. The payment service stores that key with the payment result. If the same request comes again, it returns the existing result instead of creating another payment.

# Your production database suddenly crashes, and some data may have been lost. As a backend developer, what would you do?

Answer:
First, I would check the database logs and confirm the issue. I would stop actions that could make the problem worse and inform the team. Then I would restore the database from the latest valid backup and verify the data. After recovery, I would investigate the root cause and improve the backup and recovery process.

# You release a new version of your Spring Boot API, but some old mobile app users are still using the old API format. If you change the existing API directly, their app will break. What would you do?

Answer:
I would create a new API version, such as /api/v2, instead of immediately changing /api/v1. I would keep the old version working for existing clients and give them time to migrate. After most clients move to the new version, I would deprecate the old API.

# What is the difference between authentication and authorization in a Spring Boot application?

Answer:
Authentication checks who the user is, usually through login and a JWT token. Authorization checks what that authenticated user is allowed to do. For example, a user can log in successfully but only an admin can delete another user's account.

# Your production application suddenly goes down, and many users cannot place orders. As a Java/Spring Boot developer, what would you do first?

Answer:
First, I would check the application logs, server status, database, and recent deployments to identify the problem. If a recent deployment caused the issue, I would rollback to the stable version. I would inform the team, restore the service as quickly as possible, and then investigate the root cause to prevent it from happening again.


# Your Spring Boot application uses JPA/Hibernate. In production, you suddenly get a LazyInitializationException when returning an Order with its Customer details. What could be the reason, and how would you fix it?

Answer:
The Customer data is configured for lazy loading, but the code is trying to access it after the Hibernate session is closed. I would fix it by fetching the required data inside the transaction, for example using a proper JOIN FETCH query or DTO projection. I would avoid changing everything to EAGER because it can cause unnecessary database queries.

# Your API returns 100 orders, but Hibernate is making hundreds of database queries instead of one or two. The API becomes slow. What would you check and how would you fix it?

Answer:
I would check the SQL generated by Hibernate and look for the N+1 query problem. I would optimize the query using JOIN FETCH, DTO projection, or an appropriate entity relationship strategy. The goal is to reduce unnecessary database calls and fetch the required data efficiently.

# Two users edit the same product at nearly the same time. Your application uses JPA @Version, and the second user's update fails with an optimistic locking exception. What would you do?

Answer:
I would catch the optimistic locking exception and tell the second user that the product was updated by someone else. I would ask them to refresh the latest data and try again. I would not silently overwrite the first user's changes.

# Your Spring Boot application has a shared variable inside a service, and when many users call the API at the same time, the value becomes incorrect. What could be the reason?

Answer:
The problem could be thread safety. Spring services are usually singleton objects, so multiple requests can access the same instance at the same time. I would avoid storing request-specific data in shared instance variables and use local variables or thread-safe mechanisms where required.
