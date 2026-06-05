# 📝 Note App - Full Stack MERN Application

A production-ready, full-stack notes application built with the **MERN Stack** (MongoDB, Express.js, React, Node.js). This application provides secure user authentication, email verification, password reset, and complete CRUD operations for managing personal notes.

---

## 🎯 Project Overview

**Note App** is a modern web application that allows users to:

- Create, read, update, and delete personal notes securely
- Register and authenticate with email verification
- Reset forgotten passwords with secure token validation
- Toggle between light and dark modes
- Receive real-time toast notifications for user feedback

**Live Demo:** https://note-app-omega-pied.vercel.app/

---

## 🛠️ Tech Stack

### 📱 Frontend

- **React 19.2.4** - UI library for building interactive user interfaces
- **Vite 8.0.1** - Lightning-fast build tool with HMR (Hot Module Replacement)
- **React Router DOM 7.13.2** - Client-side routing for multi-page navigation
- **Tailwind CSS 3.4.14** - Utility-first CSS framework for styling
- **Lucide React** - Modern icon library
- **React Toastify 11.0.5** - Toast notifications library
- **Vercel Analytics** - Analytics tracking

**Key Libraries:**

```json
{
  "react": "^19.2.4",
  "react-dom": "^19.2.4",
  "react-router-dom": "^7.13.2",
  "tailwindcss": "^3.4.14",
  "lucide-react": "^1.16.0",
  "react-toastify": "^11.0.5"
}
```

### 🔧 Backend

- **Node.js + Express 5.2.1** - JavaScript runtime and web framework
- **MongoDB 9.2.4** - NoSQL database for data persistence
- **JWT (jsonwebtoken 9.0.3)** - Token-based authentication
- **Bcryptjs 3.0.3** - Password hashing and encryption
- **Joi 18.1.2** - Data validation library
- **Nodemailer 8.0.5** - Email sending library
- **Express Rate Limit 8.4.1** - API rate limiting for security
- **Cookie Parser 1.4.7** - Cookie handling middleware
- **Dotenv 17.3.1** - Environment variable management

**Key Libraries:**

```json
{
  "express": "^5.2.1",
  "mongoose": "^9.2.4",
  "jsonwebtoken": "^9.0.3",
  "bcryptjs": "^3.0.3",
  "joi": "^18.1.2",
  "nodemailer": "^8.0.5",
  "express-rate-limit": "^8.4.1"
}
```

### 🔐 Security & Validation

- **JWT Authentication** - Secure token-based authentication
- **Bcrypt Password Hashing** - One-way password encryption
- **Joi Schema Validation** - Request payload validation
- **Rate Limiting** - Prevent brute force attacks on auth endpoints
- **CORS Protection** - Cross-Origin Resource Sharing configuration
- **Cookie-based Session** - Secure session management

### 📧 Email Service

- **Brevo (formerly Sendinblue)** - Email service provider via SIB API
- **Nodemailer** - Email transport and delivery

---

## ✨ Core Features

### 🔐 Authentication & Security

- ✅ **User Registration** - Email-based account creation with validation
- ✅ **Email Verification** - Confirm email before account activation
- ✅ **JWT Authentication** - Secure token-based authentication system
- ✅ **Password Security** - Bcrypt hashing with salt rounds
- ✅ **Forgot Password** - Secure password reset with email verification
- ✅ **Rate Limiting** - Prevent brute force attacks (5 attempts/15 min)

### 📝 Notes Management

- ✅ **Create Notes** - Add new notes with title and description
- ✅ **Read Notes** - View all personal notes with filtering
- ✅ **Update Notes** - Edit existing notes
- ✅ **Delete Notes** - Remove notes permanently
- ✅ **User-Specific Notes** - Each user sees only their notes

### 💡 User Experience

- ✅ **Dark Mode Toggle** - Light and dark theme support
- ✅ **Toast Notifications** - Real-time feedback for all actions
- ✅ **Protected Routes** - Access control based on authentication status
- ✅ **Responsive Design** - Mobile-friendly interface
- ✅ **Loading States** - Visual feedback during data fetching
- ✅ **Error Handling** - Comprehensive error messages

---

## 🏗️ Architecture & Workflow

### System Architecture

```
┌─────────────────────────────────────────────────────┐
│                   Note App Architecture             │
├─────────────────────────────────────────────────────┤
│                                                     │
│  ┌─────────────────────────────────────────────┐  │
│  │         Frontend (React + Vite)             │  │
│  │  ┌────────────────────────────────────────┐ │  │
│  │  │ Pages:                                 │ │  │
│  │  │ • Login / Register                     │ │  │
│  │  │ • Email Verification                  │ │  │
│  │  │ • Forgot / Reset Password             │ │  │
│  │  │ • Notes Dashboard                     │ │  │
│  │  └────────────────────────────────────────┘ │  │
│  │  ┌────────────────────────────────────────┐ │  │
│  │  │ Components:                            │ │  │
│  │  │ • Navbar, Authentication Forms         │ │  │
│  │  │ • Note Card, Note Modal                │ │  │
│  │  │ • Toast Notifications                 │ │  │
│  │  └────────────────────────────────────────┘ │  │
│  └─────────────────────────────────────────────┘  │
│                       ↕ (HTTP/REST API)           │
│  ┌─────────────────────────────────────────────┐  │
│  │     Backend (Express.js + Node.js)         │  │
│  │  ┌────────────────────────────────────────┐ │  │
│  │  │ Routes:                                │ │  │
│  │  │ • /api/auth (register, login, verify)  │ │  │
│  │  │ • /api/notes (CRUD operations)         │ │  │
│  │  └────────────────────────────────────────┘ │  │
│  │  ┌────────────────────────────────────────┐ │  │
│  │  │ Middleware:                            │ │  │
│  │  │ • Authentication (JWT Verification)   │ │  │
│  │  │ • Rate Limiting                        │ │  │
│  │  │ • Error Handling                       │ │  │
│  │  │ • CORS & Cookie Parser                │ │  │
│  │  └────────────────────────────────────────┘ │  │
│  └─────────────────────────────────────────────┘  │
│                       ↕ (Mongoose ODM)            │
│  ┌─────────────────────────────────────────────┐  │
│  │    Database (MongoDB)                      │  │
│  │  ┌────────────────────────────────────────┐ │  │
│  │  │ Collections:                           │ │  │
│  │  │ • Users (credentials, verification)   │ │  │
│  │  │ • Notes (content, metadata)            │ │  │
│  │  └────────────────────────────────────────┘ │  │
│  └─────────────────────────────────────────────┘  │
│                                                     │
└─────────────────────────────────────────────────────┘
```

### Complete User Flow

#### 1️⃣ **User Registration Flow**

```
User Visits App
    ↓
[Registration Page]
    ↓
Enter Email & Password
    ↓
Frontend Validates Input (Joi/React)
    ↓
Send POST /api/auth/register
    ↓
Backend Validates (Joi)
    ↓
Check if Email Exists
    ↓
Hash Password (Bcryptjs)
    ↓
Create User in MongoDB
    ↓
Generate Email Verification Token
    ↓
Send Verification Email (Brevo/Nodemailer)
    ↓
Frontend Shows: "Check Your Email"
    ↓
User Clicks Email Link
    ↓
Browser Navigates to /verify-email
    ↓
Send GET /api/auth/verify-email?token=xxx
    ↓
Backend Validates Token
    ↓
Mark User as Verified
    ↓
Frontend Shows: "Email Verified! Login Now"
```

#### 2️⃣ **User Login Flow**

```
User Visits Login Page
    ↓
Enter Email & Password
    ↓
Frontend Validates Input
    ↓
Send POST /api/auth/login
    ↓
Backend Finds User by Email
    ↓
Check if User Verified
    ↓
Compare Password with Hash (Bcryptjs)
    ↓
Password Correct?
  ├─ NO → Send 401 Error
  └─ YES → Generate JWT Token
    ↓
Send Token to Frontend
    ↓
Frontend Stores Token in LocalStorage
    ↓
App Verifies Token (GET /api/auth/me)
    ↓
User Authenticated!
    ↓
Redirect to Notes Dashboard
```

#### 3️⃣ **Notes Management Flow**

```
User in Notes Dashboard
    ↓
Frontend Sends GET /api/notes with JWT Token
    ↓
Backend Validates JWT
    ↓
Extract User ID from Token
    ↓
Query MongoDB: Find Notes where userId = User ID
    ↓
Return Notes to Frontend
    ↓
Frontend Displays Notes Grid
    ↓
User Actions:
    ├─ [Create] → POST /api/notes (title, description)
    │   ↓
    │   Backend Creates Note → MongoDB Insert
    │   ↓
    │   Return New Note with ID
    │   ↓
    │   Frontend: Show Toast "Note Created" → Refresh List
    │
    ├─ [Read] → Display Note Details
    │   ↓
    │   Click Note → Show in Modal
    │
    ├─ [Update] → PUT /api/notes/:noteId
    │   ↓
    │   Backend Validates Ownership
    │   ↓
    │   Update in MongoDB
    │   ↓
    │   Frontend: Show Toast "Note Updated" → Refresh
    │
    └─ [Delete] → DELETE /api/notes/:noteId
        ↓
        Backend Validates Ownership
        ↓
        Remove from MongoDB
        ↓
        Frontend: Show Toast "Note Deleted" → Refresh
```

#### 4️⃣ **Password Reset Flow**

```
User Forgot Password
    ↓
Visit /forgot-password
    ↓
Enter Email
    ↓
Send POST /api/auth/forgot-password
    ↓
Backend Finds User
    ↓
Generate Reset Token (Expires in 1 hour)
    ↓
Hash Token & Store in MongoDB
    ↓
Send Reset Link to Email
    ↓
User Clicks Link → /reset-password?token=xxx
    ↓
Enter New Password
    ↓
Send POST /api/auth/reset-password
    ↓
Backend Validates Token
    ↓
Check Token Expiry
    ↓
Hash New Password
    ↓
Update in MongoDB
    ↓
Frontend: "Password Reset Successful"
    ↓
Redirect to Login
```

---

## 📂 Project Structure

```
note-app/
├── Frontend/                      # React + Vite Frontend
│   ├── src/
│   │   ├── pages/
│   │   │   ├── Login.jsx
│   │   │   ├── Register.jsx
│   │   │   ├── Notes.jsx
│   │   │   ├── VerifyEmail.jsx
│   │   │   ├── ForgotPassword.jsx
│   │   │   └── ResetPassword.jsx
│   │   ├── components/
│   │   │   ├── Navbar.jsx
│   │   │   ├── NoteCard.jsx
│   │   │   ├── NoteModal.jsx
│   │   │   └── ProtectedRoute.jsx
│   │   ├── App.jsx               # Main app component with routing
│   │   ├── main.jsx              # Entry point
│   │   └── index.css             # Global styles
│   ├── package.json
│   ├── vite.config.js
│   └── tailwind.config.js
│
├── Backend/                       # Express.js Backend
│   ├── config/
│   │   └── db.js                 # MongoDB connection
│   ├── models/
│   │   ├── User.js               # User schema
│   │   └── Note.js               # Note schema
│   ├── routes/
│   │   ├── authRoutes.js         # Authentication endpoints
│   │   └── noteRoutes.js         # Note CRUD endpoints
│   ├── middlewares/
│   │   ├── authMiddleware.js     # JWT verification
│   │   ├── errorMiddleware.js    # Centralized error handling
│   │   └── rateLimiter.js        # Rate limiting
│   ├── controllers/
│   │   ├── authController.js     # Auth logic
│   │   └── noteController.js     # Note logic
│   ├── utils/
│   │   └── emailService.js       # Email sending
│   ├── index.js                  # Server entry point
│   ├── package.json
│   └── .env.example
│
├── screenshots/                   # UI screenshots
├── README.md
└── .gitignore
```

---

## 🚀 Getting Started

### Prerequisites

- Node.js (v14+)
- npm or yarn
- MongoDB (local or MongoDB Atlas)
- Brevo account for email service

### Backend Setup

#### Step 1: Clone Repository

```bash
git clone https://github.com/nitin01924/note-app.git
cd note-app/Backend
```

#### Step 2: Install Dependencies

```bash
npm install
```

#### Step 3: Configure Environment Variables

Create `.env` file in Backend directory:

```env
# Server Configuration
PORT=3000
NODE_ENV=development

# Database Configuration
MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/note-app?retryWrites=true&w=majority

# JWT Configuration
JWT_SECRET=your_super_secret_jwt_key_min_32_chars

# Email Service (Brevo)
BREVO_API_KEY=your_brevo_api_key
BREVO_SENDER_EMAIL=your-email@example.com
BREVO_SENDER_NAME=Note App

# Frontend URL (CORS)
CLIENT_URL=http://localhost:5173

# Token Expiry
JWT_EXPIRE=7d
RESET_TOKEN_EXPIRE=1h
```

#### Step 4: Run Backend Server

```bash
# Development mode (with nodemon)
npm run dev

# Production mode
npm start
```

Server runs on: `http://localhost:3000`

---

### Frontend Setup

#### Step 1: Navigate to Frontend

```bash
cd note-app/Frontend
```

#### Step 2: Install Dependencies

```bash
npm install
```

#### Step 3: Configure Environment Variables

Create `.env.local` file in Frontend directory:

**For Local Development:**

```env
VITE_API_URL=http://localhost:3000/api
```

**For Production:**

```env
VITE_API_URL=https://note-app-backend-971i.onrender.com/api
```

#### Step 4: Run Development Server

```bash
npm run dev
```

Frontend runs on: `http://localhost:5173`

#### Step 5: Build for Production

```bash
npm run build
```

---

## 📡 API Endpoints

### Authentication Endpoints

#### Register User

```http
POST /api/auth/register
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "SecurePassword123"
}

Response:
{
  "success": true,
  "message": "Registration successful. Check your email to verify."
}
```

#### Verify Email

```http
GET /api/auth/verify-email?token=<verification_token>

Response:
{
  "success": true,
  "message": "Email verified successfully."
}
```

#### Login User

```http
POST /api/auth/login
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "SecurePassword123"
}

Response:
{
  "success": true,
  "token": "eyJhbGc...",
  "user": {
    "id": "user_id",
    "email": "user@example.com"
  }
}
```

#### Get Current User

```http
GET /api/auth/me
Authorization: Bearer <JWT_TOKEN>

Response:
{
  "success": true,
  "user": {
    "id": "user_id",
    "email": "user@example.com"
  }
}
```

#### Forgot Password

```http
POST /api/auth/forgot-password
Content-Type: application/json

{
  "email": "user@example.com"
}

Response:
{
  "success": true,
  "message": "Reset link sent to your email."
}
```

#### Reset Password

```http
POST /api/auth/reset-password
Content-Type: application/json

{
  "token": "<reset_token>",
  "newPassword": "NewPassword123"
}

Response:
{
  "success": true,
  "message": "Password reset successfully."
}
```

### Notes Endpoints

#### Get All Notes

```http
GET /api/notes
Authorization: Bearer <JWT_TOKEN>

Response:
{
  "success": true,
  "notes": [
    {
      "_id": "note_id",
      "title": "My Note",
      "description": "Note content",
      "userId": "user_id",
      "createdAt": "2024-01-01T12:00:00Z",
      "updatedAt": "2024-01-01T12:00:00Z"
    }
  ]
}
```

#### Create Note

```http
POST /api/notes
Authorization: Bearer <JWT_TOKEN>
Content-Type: application/json

{
  "title": "My New Note",
  "description": "Note content here"
}

Response:
{
  "success": true,
  "note": {
    "_id": "new_note_id",
    "title": "My New Note",
    "description": "Note content here",
    "userId": "user_id",
    "createdAt": "2024-01-01T12:00:00Z"
  }
}
```

#### Update Note

```http
PUT /api/notes/:noteId
Authorization: Bearer <JWT_TOKEN>
Content-Type: application/json

{
  "title": "Updated Title",
  "description": "Updated content"
}

Response:
{
  "success": true,
  "note": { ... updated note ... }
}
```

#### Delete Note

```http
DELETE /api/notes/:noteId
Authorization: Bearer <JWT_TOKEN>

Response:
{
  "success": true,
  "message": "Note deleted successfully."
}
```

---

## 🔐 Security Features

### Password Security

- **Bcrypt Hashing:** Passwords hashed with salt rounds = 10
- **No Plain Text:** Passwords never stored in plain text
- **Comparison:** Bcrypt compare for authentication

### Authentication

- **JWT Tokens:** Secure token-based authentication
- **Token Expiry:** 7 days default expiration
- **Bearer Scheme:** Standard HTTP Authorization header
- **LocalStorage:** Token stored client-side

### API Security

- **Rate Limiting:** 5 attempts per 15 minutes on auth routes
- **CORS Protection:** Configured allowed origins
- **Input Validation:** Joi schema validation on all inputs
- **Error Messages:** Generic error messages to prevent info leakage

### Password Reset

- **Secure Tokens:** Hashed reset tokens in database
- **Expiry:** Reset tokens expire in 1 hour
- **Single Use:** Tokens invalidated after use
- **Email Verification:** Reset link sent to registered email

---

## 🎨 Frontend Architecture

### Routing Structure

```
/                     → Login (redirect to /notes if authenticated)
/register             → User Registration
/login                → User Login
/notes                → Protected Notes Dashboard
/verify-email         → Email Verification
/forgot-password      → Password Recovery
/reset-password       → Reset Password Form
```

### State Management

- **React Hooks:**
  - `useState` - Local component state
  - `useEffect` - Side effects and API calls
  - `useContext` - Optional for global state
- **LocalStorage:**
  - JWT token persistence
  - Theme preference (light/dark)

### Component Hierarchy

```
App (Router, Auth State)
├── Navbar (Protected Route Header)
│   ├── Logo
│   ├── Theme Toggle
│   └── Logout Button
├── Routes
│   ├── Login
│   ├── Register
│   ├── VerifyEmail
│   ├── ForgotPassword
│   ├── ResetPassword
│   └── Notes
│       ├── NoteForm
│       ├── NoteCard (List)
│       └── NoteModal (Detail/Edit)
└── ToastContainer (Notifications)
```

---

## 💾 Database Schema

### User Collection

```javascript
{
  _id: ObjectId,
  email: String (unique, required),
  password: String (hashed, required),
  isVerified: Boolean (default: false),
  verificationToken: String (hashed),
  resetToken: String (hashed),
  resetTokenExpiry: Date,
  createdAt: Date,
  updatedAt: Date
}
```

### Note Collection

```javascript
{
  _id: ObjectId,
  title: String (required),
  description: String (required),
  userId: ObjectId (reference to User),
  createdAt: Date,
  updatedAt: Date
}
```

---

## 🧪 Testing the Application

### Test Registration & Email Verification

1. Visit http://localhost:5173/register
2. Enter email and password
3. Check email inbox for verification link
4. Click verification link
5. Login with credentials

### Test Notes CRUD

1. Login to dashboard
2. Create note → Click "New Note" button
3. Read notes → View all notes on dashboard
4. Update note → Click note → Edit → Save
5. Delete note → Click delete button

### Test Password Reset

1. Visit /forgot-password
2. Enter registered email
3. Check email for reset link
4. Click link → Enter new password
5. Login with new password

### Test Rate Limiting

1. Try login with wrong password 6 times quickly
2. Should get rate limit error
3. Wait 15 minutes or check error message

---

## 📈 Performance Optimizations

- **Frontend:**
  - Code splitting with React Router
  - Lazy loading components
  - Tailwind CSS for optimized styles
  - Vite for fast builds
  - LocalStorage for token caching

- **Backend:**
  - Database indexing on frequently queried fields
  - JWT token caching
  - Connection pooling for MongoDB
  - Rate limiting to prevent abuse
  - Compressed JSON responses

---

## 🐛 Error Handling

### Frontend Error Handling

- Try-catch blocks in API calls
- Toast notifications for errors
- Fallback UI states
- Loading states during requests

### Backend Error Handling

- Centralized error middleware
- Validation error messages
- HTTP status codes (200, 400, 401, 404, 500)
- Structured error responses:

```javascript
{
  "success": false,
  "message": "Error description",
  "error": "Detailed error info"
}
```

---

## 📝 Environment Variables Reference

### Backend (.env)

```env
# Server
PORT=3000
NODE_ENV=development

# Database
MONGO_URI=mongodb+srv://...

# Authentication
JWT_SECRET=your_secret_key
JWT_EXPIRE=7d

# Email Service
BREVO_API_KEY=your_key
BREVO_SENDER_EMAIL=your@email.com

# Client
CLIENT_URL=http://localhost:5173
```

### Frontend (.env.local)

```env
VITE_API_URL=http://localhost:3000/api
```

---

## 🚀 Deployment

### Frontend Deployment (Vercel)

```bash
# Frontend is auto-deployed from GitHub to Vercel
# Update environment variables in Vercel dashboard
# VITE_API_URL → Production backend URL
```

### Backend Deployment (Render)

```bash
# Backend deployed on Render.com
# Add environment variables in Render dashboard
# Keep MongoDB Atlas connection string updated
```

---

## 📚 Key Concepts & Technologies Explained

### JWT Authentication

- Token-based authentication system
- Stateless (no session storage needed)
- Token contains user information (encoded, not encrypted)
- Used for protecting API routes
- Expires after set duration

### Bcryptjs

- One-way password hashing algorithm
- Salt rounds add randomness (10 rounds = more secure but slower)
- Prevents rainbow table attacks
- Same password produces different hash each time (salt ensures this)

### Mongoose ODM

- Object Document Mapper for MongoDB
- Provides schema validation
- Middleware hooks (pre/post)
- Indexing and querying capabilities
- Population (joining references)

### Middleware

- Functions that run before route handlers
- Can modify request/response objects
- Error handling middleware catches exceptions
- Authentication middleware verifies JWT
- Rate limiting middleware throttles requests

### CORS

- Cross-Origin Resource Sharing
- Allows frontend to make requests to different domain
- Configured with allowed origins
- Prevents unauthorized cross-domain requests

---

## 🤝 Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the ISC License - see LICENSE file for details.

---

## 👨‍💻 Author

**Nitin Kumar**

- 📧 Email: nitin981275@gmail.com
- 🔗 GitHub: [@nitin01924](https://github.com/nitin01924)
- 🌐 Portfolio: [Note App](https://note-app-omega-pied.vercel.app/)

---

## 🎯 Roadmap & Future Enhancements

### Planned Features

- [ ] Collaborative notes (share with other users)
- [ ] Rich text editor (formatting, colors, fonts)
- [ ] Note categories/tags
- [ ] Search and filter functionality
- [ ] Note export (PDF, Markdown)
- [ ] Mobile app (React Native)
- [ ] Two-factor authentication (2FA)
- [ ] Social login (Google, GitHub)

### Performance Improvements

- [ ] Image optimization
- [ ] Caching strategy
- [ ] Database query optimization
- [ ] WebSocket for real-time updates

---

## 🆘 Troubleshooting

### Backend Won't Start

```bash
# Check if port 3000 is in use
lsof -i :3000

# Kill process if needed
kill -9 <PID>

# Verify MongoDB connection
# Check MONGO_URI in .env
```

### Frontend API Connection Error

```bash
# Verify VITE_API_URL in .env.local
# Check if backend is running on correct port
# Check CORS settings in backend
# Clear browser cache and localStorage
```

### Email Not Sending

```bash
# Verify Brevo API key is correct
# Check BREVO_SENDER_EMAIL is verified in Brevo
# Check email address format
# Review Brevo dashboard for error logs
```

### Authentication Issues

```bash
# Clear localStorage: localStorage.clear()
# Remove token: localStorage.removeItem('token')
# Check JWT_SECRET matches in backend
# Verify token hasn't expired
```

---

## 📞 Support

For issues and questions:

1. Check [GitHub Issues](https://github.com/nitin01924/note-app/issues)
2. Create a new issue with detailed description
3. Email: nitin981275@gmail.com

---

<div align="center">

### ⭐ If you find this project helpful, please give it a star!

**Made with ❤️ by Nitin Kumar**

[Visit Live App](https://note-app-omega-pied.vercel.app/) • [GitHub](https://github.com/nitin01924/note-app)

</div>
