# Tell me about your self
->Good morning, and thank you for giving me this opportunity.

My name is Mahesh Bijjargi, and I am from Solapur. I completed my Bachelor of Engineering in Computer Science from Trinity Academy of Engineering, Pune.

After completing my degree, I completed a certification in Python Full Stack Development. After that, I joined a company as a paid intern, where I worked on an existing project called Variant Management System. This project is used for testing vehicle parts. I worked on adding and modifying features based on client requirements, and I was also involved in installing and deploying the application at the client's location.

After that, I pursued a CDAC certification, where I learned technologies such as  React.js, Java, Spring Boot, and SQL. I also learned the basics of DevOps technologies such as Git, GitHub, Docker, Kubernetes, and AWS EC2.

During my CDAC course, I worked on a project called UrbanSync, which is a society management system. In this project, I worked with technologies such as Java, Spring Boot, React.js, and SQL.

Overall, I have practical exposure to full-stack development, backend development, databases, and basic DevOps technologies. I am looking for an opportunity where I can apply my technical skills to real-world projects, learn new technologies, and grow as a software developer.


# Variant Management Project

The Variant Management System is an existing company project used for **testing vehicle parts**. I worked on this project based on client requirements, where I added and modified features and was also involved in installing and deploying the application at the client's location.

The system mainly manages the relationship between the **platform, model code, vehicle parts, and checkpoints**.

First, we have a **platform**. A platform represents a particular vehicle platform, for example, an XUV platform. Under one platform, there can be multiple model codes.

A **model code** is a 16-digit code that identifies a particular vehicle model. One platform can have multiple model codes.

Next, we have **parts**. For each platform, we can add the vehicle parts that need to be tested. We store the part information along with its image.

Then we have **checkpoints**. A checkpoint represents the specific location or point where a particular part needs to be checked. We connect the appropriate checkpoint with the corresponding part.

After that, we connect the **model code with the required parts**. One model code can have multiple parts. These relationships are stored in the database.

Once the configuration is completed, the data is sent to a **mobile device through APIs**. The testing team can use the mobile device to see the vehicle and its associated parts.

The tester then checks each part. If the part is correct, they click **OK**. If there is an issue, they select **NOK** and enter the reason why the part is not OK. After submitting the test results, the data is stored in the system.

The results can then be viewed again in the server-side application. We can apply filters based on things such as **date, model code, and OK/NOK status** to analyze the testing results.

My role was mainly to work on the existing system according to client requirements, including adding and modifying features and supporting the application during client installation and deployment.


# UrbanSync – Society Management System.
->I worked on a project called **UrbanSync – Society Management System**. It is a web-based application developed to digitize and manage the day-to-day activities of a residential society.

The main idea was to replace manual processes such as maintenance billing, complaints, permission requests, announcements and caretaker work tracking with a centralized web application.

The system has three types of users: **Secretary, Resident and Caretaker**.

The Secretary acts as the administrator. They can manage residents, flats, caretakers, maintenance bills, complaints, permissions and announcements.

Residents can view and pay their maintenance bills, raise complaints with images , submit permission requests and view announcements.

Caretakers can see the issues assigned to them, update the issue status and upload images as proof of completed work.

We used **Spring Security and JWT** for authentication and role-based authorization.

We also integrated external services such as **Razorpay for payments, Cloudinary for media storage and Brevo for email OTPs**.

The backend follows a three-tier architecture with presentation, service and data layers. 
My main responsibility was on the **backend development**.

I worked on the **Complaint module and Caretaker Issue module**, and I also worked on the **Scheduler service**. 

In the Complaint module, residents can raise complaints and attach images as evidence.

In the Caretaker Issue module, the Secretary can assign an issue to a caretaker. The caretaker can then update the issue status and upload media as proof of the completed work.

I also worked on the Scheduler service, which handles automated tasks such as generating monthly maintenance bills and applying daily late-payment fines.


1
12
123
1234
12345
1234
12
1