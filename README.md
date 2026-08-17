# Book Library Management System

A full-stack Spring Boot web application for managing books, users, and administrative tasks. This project features secure user authentication via JWT, a responsive web interface using Thymeleaf, and integrates with the external OpenLibrary API to fetch book data.

## 🚀 Features

- **User Authentication & Security:** Secure login and registration utilizing Spring Security and JSON Web Tokens (JWT).
- **Role-Based Access Control:** Distinct roles and dashboards for standard Users and Administrators.
- **OpenLibrary Integration:** Fetches real-time book data and metadata using the OpenLibrary API.
- **Admin Dashboard:** Dedicated interface for user management and system information monitoring.
- **Database Seeding:** Automatically initializes default data using `data.sql`.
- **Custom UI:** Frontend rendered dynamically with Thymeleaf templates and customized with interactive JavaScript (e.g., `space-bg.js`).

## 🛠️ Tech Stack

- **Backend:** Java, Spring Boot (Web, Security, Data JPA)
- **Security:** Spring Security, JWT (JSON Web Tokens)
- **Frontend:** HTML5, CSS3, JavaScript, Thymeleaf
- **Build Tool:** Maven
- **External APIs:** OpenLibrary API

## 📂 Project Structure

- `src/main/java/com/example/demo/`
  - `config/` - Application and Security configurations.
  - `controller/` - REST and Web MVC controllers handling routing.
  - `dto/` - Data Transfer Objects (Requests/Responses/OpenLibrary mapping).
  - `filter/` - Custom filters, including `JwtAuthenticationFilter`.
  - `model/` - Entity classes representing database tables.
  - `repository/` - Data access interfaces extending Spring Data JPA.
  - `service/` - Core business logic and JWT utilities.
- `src/main/resources/`
  - `templates/` - HTML Thymeleaf views (Home, Login, Admin, User, Error pages).
  - `static/` - Static assets like custom JS, CSS, and favicons.
  - `application.properties` - Main configuration file.
  - `data.sql` - Initial database seeding scripts.

---

## ⚙️ Prerequisites

Before you begin, ensure you have the following installed on your machine:

- [Java Development Kit (JDK) 17](https://adoptium.net/) or higher.
- [Node.js and npm](https://nodejs.org/) (optional, only if using the `package.json` for frontend asset management).

---

## 🚀 How to Run the Application

You have multiple options to start this application depending on your workflow.

### Option 1: Using the Makefile

If you have make installed, you can leverage the included Makefile.

```bash
make run
```

(Note: You can inspect the Makefile in the root directory for other helpful commands like `make clean` or `make build`).

### Option 2: Using the Maven Wrapper (Cross-platform)

You don't need to install Maven globally; the project comes with a Maven wrapper (mvnw).

On Windows:

```cmd
mvnw.cmd spring-boot:run
```

On macOS / Linux:

```bash
./mvnw spring-boot:run
```

### Option 3: Build a JAR and Run

To package the application into a standalone executable JAR file and run it:

```bash
./mvnw clean package
java -jar target/demo-0.0.1-SNAPSHOT.jar
```

## 🌐 Accessing the Application

Once the server successfully starts, you can access the web application in your browser at:

```
http://localhost:8080
```

### Default Routes:

- **Home:** `/`
- **Login:** `/login`
- **Signup:** `/signup`
- **Admin Dashboard:** `/admin`

---

## 💡 Important Notes & Troubleshooting

**JAR File Name:** In the run instructions (Option 4), the `target/demo-0.0.1-SNAPSHOT.jar` filename is used because the default artifact name for a `com.example.demo` package is usually `demo`. If your `pom.xml` specifies a different `<finalName>`, you will need to update the `java -jar` command accordingly.

**Server Port:** Spring Boot runs on port 8080 by default. If your `src/main/resources/application.properties` file overrides this (e.g., `server.port=9090`), make sure to update the URL when accessing the application in your browser.

**Database:** The application uses `data.sql` for initial data seeding. Ensure your database connection settings in `application.properties` are correctly configured for your local environment (whether using an H2 in-memory database or an external SQL database).

---

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.