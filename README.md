# Habit Tracker Invest

Health-focused habit tracker that invests when you don’t invest in yourself.

---

## 🧩 Tech Stack

- **Frontend:** React Native (Expo, TypeScript, NativeWind, Gluestack UI)
- **Backend:** Spring Boot (Java 17, Maven)
- **Database:** PostgreSQL (Docker container)

---

## ⚙️ Prerequisites

Make sure you have the following installed:

### Global Requirements
- [Node.js](https://nodejs.org/) (v18 or newer)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)
- [Java 17+ (Adoptium or OpenJDK)](https://adoptium.net/)
- [Maven](https://maven.apache.org/download.cgi)
- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- [Android Studio](https://developer.android.com/studio) (for running emulator)

---

## 🚀 Frontend Setup (React Native / Expo)

### 1️⃣ Navigate to the frontend folder
```bash
cd ui/habit-tracker
```

### 2️⃣ Install dependencies
```bash
npm install
```

### 3️⃣ Start the Expo development server
```bash
npx expo start
```

---

## 🗄️ Backend Setup (Spring Boot)

### 1️⃣ Install Java and Maven (if not already)

#### Check Java:
```bash
java -version
```
Output should show version 17 or higher.

#### Check Maven:
```bash
mvn -v
```
You should see the Maven version and Java home path.

---

### 2️⃣ Start PostgreSQL via Docker
```bash
docker run --name postgres-habit   -e POSTGRES_PASSWORD=password   -e POSTGRES_USER=postgres   -e POSTGRES_DB=habittracker   -p 5432:5432   -d postgres
```

This runs PostgreSQL in a Docker container on port `5432`.

---

### 3️⃣ Configure Spring Boot Database Connection

Inside your backend project (`server/src/main/resources/application.yml`):

```yaml
spring:
  datasource:
    url: jdbc:postgresql://localhost:5432/habittracker
    username: postgres
    password: password
  jpa:
    hibernate:
      ddl-auto: update
    show-sql: true
    properties:
      hibernate:
        dialect: org.hibernate.dialect.PostgreSQLDialect
server:
  port: 8080
```

---

### 4️⃣ Run the Spring Boot server

From the backend folder:

```bash
cd server
mvn spring-boot:run
```

You should see:
```
Tomcat started on port 8080 (http)
Started ServerApplication in X.XXX seconds
```

Test in your browser:
```
http://localhost:8080/
```

## ✅ Summary

| Command | Description |
|----------|-------------|
| `npm install` | Install mobile dependencies |
| `npx expo start` | Start Expo app |
| `docker run ... postgres` | Start database container |
| `mvn spring-boot:run` | Start backend API server |

---