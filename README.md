# 🔗 Linklytics - Advanced URL Shortener

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Java](https://img.shields.io/badge/Java-21-orange.svg)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4.0-brightgreen.svg)
![React](https://img.shields.io/badge/React-18.3.1-61dafb.svg)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-blue.svg)

A modern, full-stack URL shortener application with powerful analytics capabilities. Built with Spring Boot, React, and PostgreSQL, Linklytics allows users to create short, memorable links and track their performance with detailed analytics.

## ✨ Features

### 🔐 Authentication & Security
- **JWT-based Authentication** - Secure user registration and login
- **Role-based Access Control** - Protected routes and API endpoints
- **Password Encryption** - Industry-standard security practices
- **CORS Protection** - Secure cross-origin requests

### 🔗 URL Management
- **Instant URL Shortening** - Generate short URLs in seconds
- **Custom Short Codes** - Automatically generated unique identifiers
- **User Dashboard** - Manage all your shortened URLs in one place
- **Fast Redirects** - HTTP 302 redirects for optimal performance

### 📊 Analytics & Insights
- **Click Tracking** - Monitor every interaction with your links
- **Time-based Analytics** - View clicks by date range
- **Visual Graphs** - Beautiful Chart.js visualizations
- **Total Click Metrics** - Aggregate statistics across all your links
- **Click Events** - Detailed event logging with timestamps

### 🎨 User Experience
- **Responsive Design** - Works seamlessly on all devices
- **Modern UI** - Built with Tailwind CSS and Material-UI
- **Smooth Animations** - Framer Motion for delightful interactions
- **Toast Notifications** - Real-time feedback for user actions
- **Copy to Clipboard** - One-click link copying

## 🏗️ Tech Stack

### Backend
- **Java 21** - Modern Java features
- **Spring Boot 3.4.0** - Robust backend framework
- **Spring Security** - Authentication & authorization
- **Spring Data JPA** - Database abstraction layer
- **PostgreSQL** - Reliable relational database
- **JWT (jjwt 0.12.5)** - Token-based authentication
- **Lombok** - Reduced boilerplate code
- **Maven** - Dependency management

### Frontend
- **React 18.3.1** - Modern UI library
- **Vite** - Lightning-fast build tool
- **React Router DOM 7.1.1** - Client-side routing
- **Axios** - HTTP client for API calls
- **React Query** - Server state management
- **Chart.js & React-Chartjs-2** - Data visualization
- **Tailwind CSS** - Utility-first CSS framework
- **Material-UI** - React component library
- **Framer Motion** - Animation library
- **React Hook Form** - Form validation
- **React Hot Toast** - Notification system
- **Day.js** - Date manipulation

## 📁 Project Structure

```
url-shortener-project/
├── url-shortener-sb/              # Spring Boot Backend
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/url/shortener/
│   │   │   │   ├── controller/    # REST Controllers
│   │   │   │   │   ├── AuthController.java
│   │   │   │   │   ├── UrlMappingController.java
│   │   │   │   │   └── RedirectController.java
│   │   │   │   ├── models/        # JPA Entities
│   │   │   │   │   ├── User.java
│   │   │   │   │   ├── UrlMapping.java
│   │   │   │   │   └── ClickEvent.java
│   │   │   │   ├── repository/    # Data Access Layer
│   │   │   │   ├── service/       # Business Logic
│   │   │   │   ├── dtos/          # Data Transfer Objects
│   │   │   │   └── security/      # Security Configuration
│   │   │   │       ├── jwt/       # JWT Implementation
│   │   │   │       ├── WebSecurityConfig.java
│   │   │   │       └── WebConfig.java
│   │   │   └── resources/
│   │   │       └── application.properties
│   │   └── test/
│   ├── Dockerfile
│   └── pom.xml
│
└── url-shortener-react/          # React Frontend
    ├── src/
    │   ├── components/
    │   │   ├── LandingPage.jsx
    │   │   ├── LoginPage.jsx
    │   │   ├── RegisterPage.jsx
    │   │   ├── Dashboard/
    │   │   │   ├── DashboardLayout.jsx
    │   │   │   ├── CreateNewShorten.jsx
    │   │   │   ├── ShortenUrlList.jsx
    │   │   │   ├── ShortenItem.jsx
    │   │   │   ├── ShortenPopUp.jsx
    │   │   │   └── Graph.jsx
    │   │   ├── NavBar.jsx
    │   │   └── Footer.jsx
    │   ├── api/
    │   │   └── api.js             # Axios configuration
    │   ├── contextApi/
    │   │   └── ContextApi.jsx     # Global state management
    │   ├── hooks/
    │   │   └── useQuery.js        # Custom React Query hooks
    │   ├── utils/
    │   │   ├── constant.js
    │   │   └── helper.js
    │   ├── App.jsx
    │   ├── AppRouter.jsx
    │   ├── PrivateRoute.jsx
    │   └── main.jsx
    ├── public/
    ├── package.json
    ├── vite.config.js
    └── tailwind.config.js
```

## 🚀 Getting Started

### Prerequisites
- **Java 21** or higher
- **Node.js 18+** and npm
- **PostgreSQL** database
- **Maven** (included via wrapper)

### Backend Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/url-shortener-project.git
   cd url-shortener-project/url-shortener-sb
   ```

2. **Configure environment variables**
   
   Create a `.env` file in the `url-shortener-sb` directory:
   ```properties
   DATABASE_URL=jdbc:postgresql://localhost:5432/url_shortener
   DATABASE_USER=your_db_username
   DATABASE_PASS=your_db_password
   JWT_SECRET=your_super_secret_jwt_key_here
   FRONTEND_URL=http://localhost:5173
   ```

3. **Build and run the backend**
   ```bash
   # Using Maven wrapper (Unix/Mac)
   ./mvnw spring-boot:run

   # Using Maven wrapper (Windows)
   mvnw.cmd spring-boot:run

   # Or build JAR and run
   ./mvnw clean package
   java -jar target/url-shortener-sb-0.0.1-SNAPSHOT.jar
   ```

   The backend will start on `http://localhost:8080`

### Frontend Setup

1. **Navigate to the frontend directory**
   ```bash
   cd url-shortener-react
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure environment variables**
   
   Create a `.env` file in the `url-shortener-react` directory:
   ```env
   VITE_BACKEND_URL=http://localhost:8080
   ```

4. **Run the development server**
   ```bash
   npm run dev
   ```

   The frontend will start on `http://localhost:5173`

### 🐳 Docker Deployment

Build and run the backend with Docker:

```bash
cd url-shortener-sb

# Build the image
docker build -t url-shortener-backend .

# Run the container
docker run -p 8080:8080 \
  -e DATABASE_URL=jdbc:postgresql://host.docker.internal:5432/url_shortener \
  -e DATABASE_USER=your_username \
  -e DATABASE_PASS=your_password \
  -e JWT_SECRET=your_jwt_secret \
  -e FRONTEND_URL=http://localhost:5173 \
  url-shortener-backend
```

## 📡 API Endpoints

### Authentication
```http
POST   /api/auth/public/register    # Register new user
POST   /api/auth/public/login       # Login user
```

### URL Management (Authenticated)
```http
POST   /api/urls/shorten            # Create short URL
GET    /api/urls/myurls             # Get user's URLs
GET    /api/urls/analytics/{shortUrl}  # Get URL analytics
GET    /api/urls/totalClicks        # Get total clicks by date range
```

### Redirect (Public)
```http
GET    /{shortUrl}                  # Redirect to original URL
```

### Request/Response Examples

**Register User**
```json
POST /api/auth/public/register
{
  "username": "john_doe",
  "email": "john@example.com",
  "password": "securePassword123"
}
```

**Create Short URL**
```json
POST /api/urls/shorten
Authorization: Bearer {jwt_token}
{
  "originalUrl": "https://example.com/very-long-url"
}

Response:
{
  "id": 1,
  "originalUrl": "https://example.com/very-long-url",
  "shortUrl": "QN7XOa0a",
  "createdAt": "2025-11-07T10:30:00",
  "clickCount": 0
}
```

## 🎯 Key Features Explained

### URL Shortening Algorithm
- Generates unique 8-character alphanumeric codes
- Checks for collisions and regenerates if necessary
- Stores mappings in PostgreSQL with user associations

### Analytics System
- Tracks every click with timestamp
- Stores click events in separate table for scalability
- Provides aggregated views by date range
- Supports filtering by individual short URL

### Security Features
- JWT tokens with configurable expiration
- Password hashing with BCrypt
- Role-based access control (ROLE_USER)
- CORS configuration for frontend integration
- Protected API endpoints

## 🔧 Configuration

### Backend Configuration (`application.properties`)
```properties
spring.application.name=url-shortener-sb
spring.datasource.url=${DATABASE_URL}
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
jwt.secret=${JWT_SECRET}
jwt.expiration=172800000  # 48 hours
frontend.url=${FRONTEND_URL}
```

### Frontend Configuration
- Vite for fast development and optimized builds
- Tailwind CSS for responsive design
- React Query for efficient data fetching
- Context API for global state management

## 📦 Database Schema

### Users Table
- id (Primary Key)
- username (Unique)
- email (Unique)
- password (Encrypted)
- role

### URL Mappings Table
- id (Primary Key)
- original_url
- short_url (Unique, Indexed)
- user_id (Foreign Key)
- created_at
- click_count

### Click Events Table
- id (Primary Key)
- url_mapping_id (Foreign Key)
- clicked_at
- ip_address
- user_agent

```

## 🚀 Production Build

### Backend
```bash
./mvnw clean package -DskipTests
java -jar target/url-shortener-sb-0.0.1-SNAPSHOT.jar
```

### Frontend
```bash
npm run build
npm run preview
```

## 📝 Environment Variables

### Backend (.env)
| Variable | Description | Example |
|----------|-------------|---------|
| DATABASE_URL | PostgreSQL connection URL | jdbc:postgresql://localhost:5432/url_shortener |
| DATABASE_USER | Database username | postgres |
| DATABASE_PASS | Database password | your_password |
| JWT_SECRET | Secret key for JWT | your_super_secret_key |
| FRONTEND_URL | Frontend application URL | http://localhost:5173 |

### Frontend (.env)
| Variable | Description | Example |
|----------|-------------|---------|
| VITE_BACKEND_URL | Backend API base URL | http://localhost:8080 |

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

<div align="center">
  Made with ❤️ using Spring Boot & React
</div>
