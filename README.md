# 🔐 JWT Authentication System

A complete JWT-based authentication system built with Node.js, Express, MongoDB, and vanilla JavaScript. This project demonstrates secure user authentication, token-based access control, and a modern dashboard interface.

## ✨ Features

- **Secure Authentication**: JWT token-based login/signup system
- **Password Hashing**: Bcrypt for secure password storage
- **Protected Routes**: Middleware for route protection
- **Modern UI**: Responsive dashboard with user profiles
- **Real-time Data**: Live dashboard updates
- **Security Features**: Token validation, password requirements
- **Error Handling**: Comprehensive error management

## 🛠️ Tech Stack

- **Backend**: Node.js + Express.js
- **Database**: MongoDB with Mongoose
- **Authentication**: JSON Web Tokens (JWT)
- **Security**: bcryptjs for password hashing
- **Frontend**: Vanilla JavaScript + HTML5 + CSS3
- **Styling**: Modern gradient designs with animations

## 📁 Project Structure

```
jwt-auth-system/
├── server.js              # Main server file
├── package.json           # Dependencies and scripts
├── .env                   # Environment variables
├── public/               # Frontend files
│   ├── index.html        # Login/Signup page
│   └── dashboard.html    # Protected dashboard
└── README.md             # This file
```

## 🚀 Quick Setup

### 1. Prerequisites
- Node.js (v14 or higher)
- MongoDB (local or cloud)
- npm or yarn

### 2. Installation

```bash
# Clone or create project folder
mkdir jwt-auth-system
cd jwt-auth-system

# Install dependencies
npm install express mongoose bcryptjs jsonwebtoken cors dotenv

# Install development dependencies
npm install --save-dev nodemon
```

### 3. Environment Setup

Create a `.env` file in the root directory:

```env
MONGODB_URI=mongodb://localhost:27017/jwtauth
JWT_SECRET=your-super-secret-jwt-key-change-this-in-production
PORT=3000
NODE_ENV=development
```

### 4. Database Setup

**Option A: Local MongoDB**
```bash
# Install MongoDB locally
# Start MongoDB service
mongod

# Create database (automatic on first connection)
```

**Option B: MongoDB Atlas (Cloud)**
```bash
# Create account at mongodb.com/atlas
# Create cluster and get connection string
# Update MONGODB_URI in .env file
```

### 5. Create Project Files

Create the following folder structure:
```bash
mkdir public
# Add all the provided files to their respective locations
```

### 6. Start the Server

```bash
# Development mode (with auto-restart)
npm run dev

# Production mode
npm start
```

## 🔧 API Endpoints

### Authentication Routes

#### POST /api/signup
Create a new user account.

**Request Body:**
```json
{
  "username": "john_doe",
  "email": "john@example.com",
  "password": "securepassword123"
}
```

**Response:**
```json
{
  "success": true,
  "message": "User created successfully",
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "user": {
    "id": "user_id",
    "username": "john_doe",
    "email": "john@example.com"
  }
}
```

#### POST /api/login
Authenticate existing user.

**Request Body:**
```json
{
  "email": "john@example.com",
  "password": "securepassword123"
}
```

**Response:**
```json
{
  "success": true,
  "message": "Login successful",
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "user": {
    "id": "user_id",
    "username": "john_doe",
    "email": "john@example.com"
  }
}
```

### Protected Routes

#### GET /api/dashboard
Get user dashboard data (requires authentication).

**Headers:**
```
Authorization: Bearer <jwt_token>
```

**Response:**
```json
{
  "success": true,
  "message": "Welcome to your dashboard!"
}


