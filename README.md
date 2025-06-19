# Airbnb Clone Project

## 🚀 Objective
This project aims to be a complete replica of the widely-used lodging reservation service AirBnB. The objective is to create a fully operational web application where users can explore property listings, access detailed information about properties, and finalize bookings. The project encompasses frontend development, backend APIs, database architecture, and deployment.

## 🏆 Project Goals  
Upon finishing this project, participants will:  
- Acquire the ability to create responsive UI/UX designs  
- Gain insight into structuring a complex web application  
- Experience collaborative teamwork with designated roles  
- Enhance skills in component-driven frontend architecture  
- Learn optimal practices for web application development
- Master collaborative team workflows using GitHub.
- Deepen their understanding of backend architecture and database design principles.
- Implement advanced security measures for API development.
- Gain proficiency in designing and managing CI/CD pipelines for efficient deployment.
- Strengthen their ability to document and plan complex software projects effectively.
- Develop an understanding of integrating technologies like Django, MySQL, and GraphQL in a unified ecosystem.


## ⚙️ Technology Stack
### Frontend:
  HTML, CSS, JavaScript (React or similar framework)
  - **HTML (Hypertext Markup Language)** is the standard language used to create the structure of web pages. It defines the layout and elements that make up a webpage.
  - **CSS (Cascading Style Sheets)** is used for styling HTML elements. It controls the visual presentation, including colors, fonts, layouts, and responsiveness.
  - **JavaScripts** is a programming language that enables dynamic content on weeb pages. It allows for interactivity, maniplation of the Document Object Model (DOM), and integration with backend services.
  - **React (or similar framework)** refers to a modern JavaScript library or framework used for building user interfaces, especially single-page applications.
### Backend:
  Django, Django REST Framework, PostgreSQL, GraphQL, Celery, Redis, CI/CD Pipelines, Docker
  - **Django**: A high-level Python web framework that encourages rapid development and clean, pragmatic design. It simplifies backend development with built-in features like authentication, database management, and an admin interface.
  - **Django REST Framework**: An extension of Django specifically for building Web APIs. It provides tools to create RESTful APIs easily and includes features for serialization, authentication, and view management.
  - **PostgreSQL**: An advanced, open-source relational database management system that supports SQL compliance and numerous advanced features. It is often chosen for its reliability, feature set, and performance.
  - **GraphQL**: A query language for APIs that allows clients to request only the data they need. It enables more efficient data retrieval and a more flexible interaction with the server compared to traditional REST APIs.
  - **Celery**: An asynchronous task queue/job queue based on distributed message passing. It is typically used for handling background tasks, such as sending emails or processing data, allowing the web application to remain responsive.
  - **Redis**: An in-memory key-value data structure store often used as a database, cache, and message broker. In a web application context, it can optimize performance by caching frequently accessed data.
  - **CI/CD Pipelines**: Continuous Integration/Continuous Deployment pipelines are methodologies that automate the process of integrating code changes, testing, and deploying applications. They help ensure code quality and enable faster delivery of new features or updates.
  - **Docker**: Containerization tool for consistent development and deployment environments.
    
### Version Control:
  Git and GitHub
### Design Tools:
  Figma for UI/UX design


## 🛠️ Features Overview
1. ### API Documentation
   - **OpenAPI Standard**: The backend APIs are documented using the OpenAPI standard to ensure clarity and ease of integration.
   - **Django REST Framework**: Provides a comprehensive RESTful API for handling CRUD operations on user and property data.
   - **GraphQL**: Offers a flexible and efficient query mechanism for interacting with the backend.
  
2. ### User Authentication
   - **Endpoint**: ```/users/, /users/{user_id}/```
   - **Features**: Register new users, authenticate, and manage user profiles.
3. ### Property Management
   - **Endpoints**: ```/properties/,/properties/{property_id}/```
   - **Features: Create, update, retrieve, and delete property listings.
4. ### Booking System
   - **Endpoints**: ```/bookings/, /bookings/{booking_id}/```
   - **Features: Make, update, and manage bookings, including check-in and check-out details.
5. ### Payment Processing
   - **Endpoints**: ```/payments/```
   - **Features: Create, update, retrieve, and delete property listings.
6. ### Review System
   - **Endpoints**: ```/reviews/, /reviews/{review_id}/```
   - **Features: Create, update, retrieve, and delete property listings.
7. ### Database Optimizations
   - **Indexing**: Implement indexes for fast retrieval of frequently accessed data.
   - **Caching**: Use caching strategies to reduce database load and improve performance.


## 📌 Database Design
### Key Entities
1. **Users**
   - **UserID**: Unique identifier for each user (Primary Key).
   - **Username**: The name chosen by the user for login and display.
   - **Email**: The user's email address for communication and notifications.
   - **PasswordHash**: A hashed version of the user's password for security.
   - **UserType**: Indicates whether the user is a guest or a host.
2. **Properties**
   - **PropertyID**: Unique identifier for each property (Primary Key).
   - **UserId**: Foreign key linking to the Users table, representing the host (owner of the property).
   - **Title**: The title of the property listing.
   - **Description**: A detailed description of the property.
   - **Location**: The geographical location of the property.
3. **Bookings**
   - **BookingID**: Unique identifier for each booking (Primary Key).
   - **UserID**: Foreign key linking to the Users table, representing the guest making the booking.
   - **PropertyID**: Foreign key linking to the Properties table, representing the booked property.
   - **CheckInDate**: The date when the quest checks in.
   - **CheckOutDate**: The date when the guest checks out.
   - **BookingStatus**: Status of the booking (e.g., confirmed, canceled, completed).
4. **Reviews**
   - **ReviewID**: Unique identifier for each review (Primary Key).
   - **PropertyID**: Foreign key linking to the Properties table, representing the property being reviewed.
   - **UserID**: Foreign Key linking to the Users table, representing the user who wrote the review.
   - **Rating**: A numerical rating given by the user (e.g., 1 - 5 stars).
   - **Comment**: Textual feedback provided by the user.
5. **Payments**
   - **PaymentID**: Unique identifier for each payment (Primary Key).
   - **BookingID**: Foreign key linking to the Bookings table, representing the booking associated with the payment.
   - **UserID**: Foreign Key linking to the users table, representing the guest who made the payment.
   - **Amount**: The total amount paid for the booking.
   - **PaymentMethod**: The method used for payment (e.g., credit card, PayPal).
   - **PaymentStatus**: Status of the payment(e.g., completed, pending, failed).
     
### Entity Relationships
- **Users <-> Properties**: A user can own multiple properties (one-to-many relationship). Each property is associated with one user (the host).
- **Users <-> Bookings**: A single (guest) user can have multiple bookings (one-to-many relationship). Each booking is made by one user.
- **Properties <-> Bookings**: A single property can have multiple bookings over time, but each booking is for one specific property (one-to-many relationship).
- **Users <-> Reviews**: A user can write multiple reviews (one-to-many relationship). Each review is linked to one user.
- **Properties <-> Reviews**: A property can have multiple reviews (one-to-many relationship). Each review is linked to one specific property.
- **Bookings <-> Payments**: Each booking can have one associated payment (one-to-one relationship). Each payment corresponds to one specific booking.
- **Users <-> Payments**: A user can make multiple payments (one-to-many relationship). Each payment is associated with one specific user.

This structure outlines the essential components of the database, ensuring that all necessary information is captured and that relationships between entities are clearly defined.

### API Security
#### Key Security Measures
1. **Authentication**
   - **Description**:  Authentication is the process of verifying the identity of a user or system. This will be implemented using secure methods such as OAuth 2.0 or JSON Web Tokens (JWT).
   - **Importance**: Ensures that only legitimate users can access the API, protecting sensitive user data and preventing unauthorized access to the system.
2. **Authorization**
   - **Description**: Authorization determines what an authenticated user is allowed to do. Role-based access control (RBAC) will be used to manage permissions for different user types (e.g., guests and hosts).
   - **Importance**: Prevents users from accessing resources or performing actions that they are not permitted to, thereby protecting critical functionalities and data integrity.
3. **Rate Limiting**
   - **Description**: Rate limiting restricts the number of requests a user can make to the API within a specified time frame. This will help mitigate abuse and ensure fair usage of the API.
   - **Importance**: Protects the API from denial-of-service (DoS) attacks and helps maintain performance by preventing any single user from overwhelming the system with excessive requests.
  
4. **Data Encryption**
   - **Description**: All sensitive data, including user credentials and payment information, will be encrypted both in transit (using HTTPS) and at rest (using encryption algorithms).
   - **Importance**: Protects user data from interception during transmission and unauthorized access in storage, ensuring confidentiality and integrity of sensitive information.
  
5. **Input Validation**
   - **Description**: All inputs to the API will be validated to prevent injection attacks (e.g., SQL injection, cross-site scripting).
   - **Importance**: Ensures that only valid data is processed by the API, reducing the risk of attacks that could compromise the system or lead to data breaches.
  
6. **Logging and Monitoring**
   - **Description**: Implement logging and monitoring to track API usage and detect suspicious activities. This includes logging failed login attempts and monitoring for unusual patterns.
   - **Importance**: Provides visibility into API usage, helps identify potential security incidents, and enables timely responses to threats.

#### Importance of Security in Key Areas
- **Protecting User Data**: User data, including personal information and passwords, must be safeguarded to maintain trust and comply with data protection regulations (e.g., GDPR, CCPA). A breach could lead to identity theft and legal consequences.
- **Securing Payments**: Payment information is highly sensitive and must be protected to prevent fraud and financial loss. Implementing strong security measures ensures that users can make transactions with confidence.
- **Maintaining System Integrity**: Security measures help prevent unauthorized access and modifications to the system, ensuring that the application functions as intended and that data remains accurate and reliable.
- **Building User Trust**: A strong security posture reassures users that their data and transactions are safe, fostering trust and encouraging continued engagement with the platform.

By prioritizing API security, we can create a robust and trustworthy platform that protects users and their data while ensuring a smooth and reliable experience.

## CI/CD Pipeline
### CI/CD
CI/CD stands for continuous Integration and continuous Deployment (or continuous Delivery).
CI/CD pipelines are automated workflows that facilitate the process of integrating code changes, testing them, and deploying applications to production. The pipeline typically consists of the following stages:
1. **Continuous Integration (CI)**: This stage involves automatically building and testing code changes as they are merged into the main branch. It ensures that new code integrates seamlessly with the existing codebase and that any issues are detected early.

2. **Continuous Delivery (CD)**: This stage automates the deployment of code to production or staging environments. It allows teams to release updates quickly and reliably, ensuring that the application is always in a deployable state.

3. **Continuous Deployment (CD)**: An extension of Continuous Delivery, this stage automatically deploys every change that passes the testing stage to production without manual intervention.

### Importance of CI/CD Pipelines for the project
- **Faster Development**: CI/CD pipelines streamline the development process by automating repetitive tasks, allowing developers to focus on writing code rather than managing deployments.
- **Improved Code Quality**: Automated testing within the CI/CD pipeline ensures that code changes are thoroughly tested before they are deployed, reducing the likelihood of bugs and improving overall code quality.
- **Rapid Feedback**: Developers receive immediate feedback on their code changes, enabling them to address issues quickly and maintain a high level of code quality.
- **Consistent Deployments**: Automated deployment processes reduce the risk of human error and ensure that deployments are consistent across different environments.
- **Enhanced Collaboration**: CI/CD pipelines promote collaboration among team members by providing a shared framework for integrating and deploying code changes.

### Tools for CI/CD Pipelines
- **GitHub Actions**: A powerful automation tool that allows you to create workflows directly within your GitHub repository. It can be used for building, testing, and deploying applications.

- **GitLab CI/CD**: Integrated CI/CD capabilities within GitLab, providing a seamless way to manage your code repository, build, test, and deploy applications.
- **Jenkins**: An open-source automation server that enables you to set up CI/CD pipelines with a wide range of plugins for different tasks and integrations.
- **CircleCI**: A cloud-based CI/CD tool that automates the software development process, allowing for easy integration with various version control systems.
- **Travis CI**: A continuous integration service that automatically builds and tests code changes in GitHub repositories.
- **Docker**: While primarily a containerization tool, Docker can be integrated into CI/CD pipelines to ensure that applications are built, tested, and deployed in consistent environments.


## UI/UX Design Planning.
### Design Objectives
  - **Enhance User Experience**: Ensure that the interface is intuitive and easy to navigate.
  - **Visual Appeal**: Create a visually appealing design that aligns with the brand identity.
  - **Accessibility**: Design for users of all abilities and backgrounds.
  - **Consistency**: Maintain a consistent look and feel across all pages.
### Key Features
- Responsive design for mobile and desktop
- Easy navigation through well-defined menus and buttons.
- Quick loading times to improve user satisfaction.
- Clear calls to action to guide users through the booking process.

### Primary Pages Descriptions

| Page Name                    | Description                                                                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| **Property Listing View**    | Displays a grid of available properties with images, brief descriptions, and filtering options. Users can sort by price, location, and amenities.   |
| **Listing Detailed View**    | Provides in-depth information about a selected property, including high-resolution images, detailed descriptions, amenities, and user reviews. Users can check availability and book directly from this page. |
| **Simple Checkout View**     | A streamlined checkout process that allows users to enter their details, select payment options, and confirm bookings quickly. The design minimizes distractions to enhance focus on completing the booking. |

#### Importance of User-Friendly Design in a Booking System
A user-friendly design is crucial in a booking system as it directly impacts user satisfaction and conversion rates. An intuitive interface reduces confusion and frustration, making it easier for users to find and book properties. By prioritizing usability, we can enhance the overall experience, leading to increased trust and repeat customers. A well-designed system not only meets user needs but also encourages them to complete their bookings, ultimately driving business success.

### Figma Design Specifications
#### Color Styles
- **Primary Color**: #FF5A5F
- **Secondary Color**: #008489
- **Background Color**: #FFFFFF
- **Text Color**: #222222
- **Secondary Text Color**: #717171

#### Typography
- **Primary Font**: Circular, Medium (500), 16px
- **Headings**: Circular, Bold (700), 24px-32px
- **Secondary Text**: Circular, Book (400), 14px

### Importance of Identifying Design Properties in a Mockup Design
Identifying design properties in a mockup is essential for several reasons:
1. **Consistency**: Establishing a clear set of design properties ensures that all elements of the user interface are cohesive. This consistency helps users understand the interface better and reduces cognitive load.
2. **Guidance for Development**: Well-defined design properties serve as a reference for developers, ensuring that the final product aligns closely with the intended design vision.
3. **User Experience**: Clear design properties enhance user experience by creating familiarity. When users encounter consistent styles, they can navigate more intuitively.
4. **Feedback and Iteration**: Identifying these properties allows for easier feedback and iteration during the design process, making it simpler to make adjustments based on user testing or stakeholder input.
5. **Brand Identity**: Consistent use of colors and typography reinforces brand identity and helps create a memorable experience for users.

## UI Component Patterns
### Planned Components
1. **Navbar**
   - Logo
   - Navbar
   - Search bar
   - User navigation
   - Responsive menu
2. **Property Card**
   - Property image
   - Basic details (price, location, rating)
   - Favorite button
   - Responsive layout
3. **Footer**
   - Site links
   - Company information
   - Social media links
   - copyright information

Each component will be designed for reusability and consistency across the application.

## 👥 Project Roles and Responsibilities

| Roles                        | Responsibilities                                                      |
|------------------------------|-----------------------------------------------------------------------|
| **Project Manager**          | Oversees timeline, coordinates team, manages deliverables             |
| **Frontend Developers**      | Implements UI components, ensures responsive design                   |
| **Backend Developers**       | Builds APIs, manages database, implements business logic              |
| **Designers**                | Creates mockups, maintains design system, ensures UX qualit           |
| **QA/Testers**               | Writes test cases, performs testing, reports bugs                     |
| **DevOps Engineers**         | Manages deployment, CI/CD pipeline, server infrastructure             |
| **Product Owner**            | 	Defines requirements, prioritizes features, represents stakeholders  |
| **Scrum Master**             | Facilitates agile processes, removes blockers, organizes meetings     |
