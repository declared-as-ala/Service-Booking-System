# Service Booking System

A full-stack web application for managing service bookings built with Angular and Spring Boot. This system enables clients to book services and companies to manage their service offerings, with role-based access control and secure authentication.

## 🚀 Features

- **User Authentication & Authorization**
  - User registration and login
  - Role-based access control (Client and Company)
  - JWT-based secure authentication
  - Separate signup flows for clients and companies

- **Client Features**
  - Client dashboard
  - Service booking functionality
  - View and manage bookings

- **Company Features**
  - Company dashboard
  - Manage service offerings
  - Track bookings and clients

- **Modern UI**
  - Responsive design with NG-Zorro Ant Design
  - Server-side rendering (SSR) support
  - Intuitive user interface

## 🛠️ Tech Stack

### Backend
- **Spring Boot 3.2.5** - Java framework for building REST APIs
- **Java 22** - Programming language
- **Spring Data JPA** - Data persistence
- **Spring Security** - Security framework
- **JWT** - JSON Web Tokens for authentication
- **MySQL** - Relational database
- **Maven** - Dependency management
- **Lombok** - Java library to reduce boilerplate code

### Frontend
- **Angular 17** - Modern web framework
- **TypeScript** - Type-safe JavaScript
- **NG-Zorro Ant Design** - Enterprise Angular UI component library
- **RxJS** - Reactive programming
- **Angular SSR** - Server-side rendering support
- **SCSS** - CSS preprocessor

## 📋 Prerequisites

Make sure you have the following tools installed before setting up the application:

- **Node.js** - v16 or higher ([Download Node.js](https://nodejs.org/))
- **Angular CLI** - Install globally:
  ```bash
  npm install -g @angular/cli
  ```
- **Java Development Kit (JDK)** - Version 22 ([Download JDK](https://www.oracle.com/java/technologies/downloads/))
- **Maven** - Build tool ([Download Maven](https://maven.apache.org/))
- **MySQL** - Database server ([Download MySQL](https://dev.mysql.com/downloads/mysql/))

## 🔧 Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/declared-as-ala/Service-Booking-System.git
cd Service-Booking-System
```

### 2. Database Configuration

1. Create a new MySQL database:
   ```sql
   CREATE DATABASE service_booking_db;
   ```

2. Configure database connection in `Backend/src/main/resources/application.properties`:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/service_booking_db
   spring.datasource.username=your_db_username
   spring.datasource.password=your_db_password
   spring.jpa.hibernate.ddl-auto=update
   ```
   
   > **Note:** Update the username, password, and database URL according to your MySQL configuration.

### 3. Backend Setup

1. Navigate to the Backend directory:
   ```bash
   cd Backend
   ```

2. Build and run the Spring Boot application:
   ```bash
   # Using Maven wrapper (Windows)
   mvnw.cmd spring-boot:run
   
   # Using Maven wrapper (Linux/Mac)
   ./mvnw spring-boot:run
   
   # Or using Maven directly
   mvn spring-boot:run
   ```
   
   The backend API will be available at `http://localhost:8080` (or the port configured in application.properties)

### 4. Frontend Setup

1. Navigate to the Frontend directory:
   ```bash
   cd Frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Run the Angular development server:
   ```bash
   ng serve
   # or
   npm start
   ```
   
   The frontend application will be available at `http://localhost:4200`

4. Build for Production:
   ```bash
   ng build
   ```

5. Build with Server-Side Rendering (SSR):
   ```bash
   npm run build
   npm run serve:ssr:ServicesBookingSystem
   ```

## 🎯 Usage

### Access the Application

- Open your browser and navigate to `http://localhost:4200`

### Getting Started

1. **Register as a Client:**
   - Click on "Sign Up" and select "Client"
   - Fill in your details and create an account
   - Access the client dashboard to book services

2. **Register as a Company:**
   - Click on "Sign Up" and select "Company"
   - Fill in your company details and create an account
   - Access the company dashboard to manage services

3. **Login:**
   - Use your credentials to log in
   - You'll be redirected to the appropriate dashboard based on your role

## 📁 Project Structure

```
Service-Booking-System/
├── Backend/                          # Spring Boot backend
│   ├── src/
│   │   └── main/
│   │       ├── java/
│   │       │   └── com/vinn/ServiceBookingSystem/
│   │       │       ├── configs/      # Security and CORS configuration
│   │       │       ├── controller/   # REST controllers
│   │       │       ├── services/     # Business logic
│   │       │       │   ├── authenntication/  # Auth services
│   │       │       │   ├── jwt/      # JWT services
│   │       │       │   └── user/     # User services
│   │       │       ├── repository/  # Data access layer
│   │       │       ├── entity/       # Entity models
│   │       │       ├── dto/          # Data transfer objects
│   │       │       ├── enums/        # Enumerations
│   │       │       └── util/         # Utility classes
│   │       └── resources/
│   │           └── application.properties
│   └── pom.xml
├── Frontend/                         # Angular frontend
│   ├── src/
│   │   └── app/
│   │       ├── basic/               # Authentication components
│   │       │   ├── components/
│   │       │   │   ├── login/       # Login component
│   │       │   │   ├── signup/      # General signup
│   │       │   │   ├── signup-client/    # Client signup
│   │       │   │   └── signup-company/   # Company signup
│   │       │   └── services/        # Auth services
│   │       ├── client/              # Client module
│   │       │   └── pages/
│   │       │       └── client-dashboard/
│   │       ├── company/             # Company module
│   │       │   └── pages/
│   │       │       └── company-dashboard/
│   │       └── DemoNgZorroAntdModule.ts
│   └── package.json
└── README.md
```

## 🔐 Security Features

- JWT token-based authentication
- Role-based access control (Client/Company)
- Spring Security integration
- CORS configuration for cross-origin requests
- Password encryption
- Secure API endpoints

## 📝 API Endpoints

The application provides RESTful APIs for:
- Authentication (login, signup for clients and companies)
- User management
- Service booking operations
- Dashboard data retrieval

## 🐛 Troubleshooting

- **Database Connection Issues:** Ensure MySQL is running and credentials in `application.properties` are correct
- **Port Conflicts:** Check if ports 8080 (backend) and 4200 (frontend) are available
- **Dependencies:** Run `npm install` in the Frontend directory if you encounter module errors
- **Build Errors:** Ensure JDK 22 is installed and Maven is properly configured
- **CORS Issues:** Verify CORS configuration in `SimpleCorsFilter.java` matches your frontend URL

## 🚀 Deployment

### Backend Deployment
- Build the JAR file: `mvn clean package`
- Run the JAR: `java -jar target/ServiceBookingSystem-0.0.1-SNAPSHOT.jar`

### Frontend Deployment
- Build for production: `ng build --configuration production`
- Deploy the `dist/` folder to your web server
- For SSR: Build and run the SSR server as shown in setup instructions

## 📄 License

This project is licensed under the MIT License.

## 👨‍💻 About the Author

**Ala Missaoui**

- 📧 Email: [alamissaoui.dev@gmail.com](mailto:alamissaoui.dev@gmail.com)
- 🔗 GitHub: [@declared-as-ala](https://github.com/declared-as-ala)

This project was forked and enhanced to demonstrate full-stack development skills with Spring Boot and Angular, focusing on building a complete service booking system with role-based access control, JWT authentication, and modern UI components.

## 🙏 Acknowledgments

- Original project by [thanthtooaung-coding](https://github.com/thanthtooaung-coding/Service-Booking-System)
- Built with Spring Boot 3.2.5, Angular 17, and NG-Zorro Ant Design

---

**Note:** This project demonstrates a complete full-stack application with authentication, role-based access control, and modern web development practices. The application supports both client and company user types with separate dashboards and functionalities.
