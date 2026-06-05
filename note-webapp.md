# 📝 Note App - Full Stack MERN Application

<div align="center">

![Note App](https://img.shields.io/badge/MERN-Stack-blue?style=for-the-badge)
![React](https://img.shields.io/badge/React-19.2.4-61DAFB?style=for-the-badge&logo=react)
![Node.js](https://img.shields.io/badge/Node.js-Express-green?style=for-the-badge&logo=node.js)
![MongoDB](https://img.shields.io/badge/MongoDB-9.2.4-13AA52?style=for-the-badge&logo=mongodb)
![License](https://img.shields.io/badge/License-ISC-yellow?style=for-the-badge)

**A modern, secure, and feature-rich notes application built with cutting-edge web technologies**

[🌐 Live Demo](https://note-app-omega-pied.vercel.app/) • [📂 GitHub](https://github.com/nitin01924/note-app) • [📧 Contact](mailto:nitin981275@gmail.com)

</div>

---

## ✨ Key Features

<table>
<tr>
<td>

### 🔐 Authentication
- ✅ Email Registration
- ✅ Email Verification
- ✅ Secure Login/Logout
- ✅ Password Recovery
- ✅ JWT Token Management

</td>
<td>

### 📝 Notes Management
- ✅ Create Notes
- ✅ Read/View Notes
- ✅ Edit Notes
- ✅ Delete Notes
- ✅ User-Specific Access

</td>
<td>

### 🎨 User Experience
- ✅ Dark Mode Toggle
- ✅ Toast Notifications
- ✅ Responsive Design
- ✅ Loading States
- ✅ Error Handling

</td>
</tr>
</table>

---

## 🛠️ Tech Stack

<div align="center">

| Frontend | Backend | Database | Security |
|----------|---------|----------|----------|
| ![React](https://img.shields.io/badge/React-19.2.4-61DAFB?style=flat&logo=react) | ![Node.js](https://img.shields.io/badge/Node.js-Runtime-339933?style=flat&logo=node.js) | ![MongoDB](https://img.shields.io/badge/MongoDB-9.2.4-13AA52?style=flat&logo=mongodb) | ![JWT](https://img.shields.io/badge/JWT-Auth-000000?style=flat) |
| ![Vite](https://img.shields.io/badge/Vite-8.0.1-646CFF?style=flat&logo=vite) | ![Express](https://img.shields.io/badge/Express-5.2.1-000000?style=flat&logo=express) | ![Mongoose](https://img.shields.io/badge/Mongoose-ODM-880000?style=flat) | ![Bcrypt](https://img.shields.io/badge/Bcryptjs-Hashing-FF6B6B?style=flat) |
| ![Tailwind](https://img.shields.io/badge/Tailwind-CSS-06B6D4?style=flat&logo=tailwindcss) | ![Nodemailer](https://img.shields.io/badge/Nodemailer-Email-EA4335?style=flat) | | ![Rate Limit](https://img.shields.io/badge/Rate_Limit-Protection-FFA500?style=flat) |
| ![React Router](https://img.shields.io/badge/Router-7.13.2-CA4245?style=flat&logo=react-router) | ![Joi](https://img.shields.io/badge/Joi-Validation-0096D6?style=flat) | | ![CORS](https://img.shields.io/badge/CORS-Protection-9C27B0?style=flat) |

</div>

---

## 🏗️ System Architecture

<div align="center">

```
┌─────────────────────────────────────────┐
│       Frontend (React + Vite)          │
│  • Login • Register • Notes Dashboard   │
│  • Email Verification • Password Reset  │
└──────────────────┬──────────────────────┘
                   │ HTTP/REST API
                   ↓
┌─────────────────────────────────────────┐
│     Backend (Express.js + Node.js)     │
│  • Authentication Routes                │
│  • Notes CRUD Endpoints                 │
│  • JWT Middleware & Rate Limiting       │
└──────────────────┬──────────────────────┘
                   │ Mongoose ODM
                   ↓
┌─────────────────────────────────────────┐
│   Database (MongoDB Atlas/Local)       │
│  • Users Collection                     │
│  • Notes Collection                     │
└─────────────────────────────────────────┘
```

</div>

---

## 📊 User Flows

### Registration & Email Verification
```
Registration → Validation → Hash Password → Create User → Send Email → Verify Link → Account Active
```

### Login Process
```
Enter Credentials → Validate → Compare Hash → Generate JWT → Store Token → Authenticated
```

### Notes Management
```
Fetch Notes → Display Grid → User Action → API Call → Database Update → Refresh UI
```

### Password Reset
```
Forgot Password → Send Email → Verify Token → New Password → Update DB → Success
```

---

## 📂 Project Structure

```
note-app/
│
├─ Frontend/                          # React + Vite Application
│  ├─ src/
│  │  ├─ pages/
│  │  │  ├─ Login.jsx
│  │  │  ├─ Register.jsx
│  │  │  ├─ Notes.jsx
│  │  │  ├─ VerifyEmail.jsx
│  │  │  └─ ForgotPassword.jsx
│  │  ├─ components/
│  │  │  ├─ Navbar.jsx
│  │  │  ├─ NoteCard.jsx
│  │  │  └─ ProtectedRoute.jsx
│  │  └─ App.jsx
│  └─ package.json
│
├─ Backend/                           # Express.js Application
│  ├─ config/db.js
│  ├─ models/ (User.js, Note.js)
│  ├─ routes/ (authRoutes.js, noteRoutes.js)
│  ├─ controllers/ (authController.js, noteController.js)
│  ├─ middlewares/ (authMiddleware.js, rateLimiter.js)
│  ├─ utils/emailService.js
│  └─ index.js
│
└─ README.md
```

---

## 🚀 Quick Start

### Prerequisites
- Node.js v14+
- MongoDB (Atlas or Local)
- Brevo API Key (for emails)

### Backend Setup

```bash
# 1. Clone & Navigate
git clone https://github.com/nitin01924/note-app.git
cd note-app/Backend

# 2. Install Dependencies
npm install

# 3. Create .env file
cat > .env << EOF
PORT=3000
MONGO_URI=your_mongodb_uri
JWT_SECRET=your_secret_key_min_32_chars
BREVO_API_KEY=your_api_key
BREVO_SENDER_EMAIL=your_email@example.com
CLIENT_URL=http://localhost:5173
JWT_EXPIRE=7d
EOF

# 4. Start Server
npm run dev
```

### Frontend Setup

```bash
# 1. Navigate to Frontend
cd note-app/Frontend

# 2. Install Dependencies
npm install

# 3. Create .env.local
echo "VITE_API_URL=http://localhost:3000/api" > .env.local

# 4. Start Development Server
npm run dev
```

**Access the app at:** `http://localhost:5173`

---

## 📡 API Endpoints

<table>
<tr>
<th>Method</th>
<th>Endpoint</th>
<th>Description</th>
<th>Auth</th>
</tr>
<tr>
<td>POST</td>
<td>/api/auth/register</td>
<td>Register new user</td>
<td>❌</td>
</tr>
<tr>
<td>POST</td>
<td>/api/auth/login</td>
<td>Login user</td>
<td>❌</td>
</tr>
<tr>
<td>GET</td>
<td>/api/auth/verify-email</td>
<td>Verify email address</td>
<td>❌</td>
</tr>
<tr>
<td>GET</td>
<td>/api/auth/me</td>
<td>Get current user</td>
<td>✅</td>
</tr>
<tr>
<td>POST</td>
<td>/api/auth/forgot-password</td>
<td>Request password reset</td>
<td>❌</td>
</tr>
<tr>
<td>POST</td>
<td>/api/auth/reset-password</td>
<td>Reset password</td>
<td>❌</td>
</tr>
<tr>
<td>GET</td>
<td>/api/notes</td>
<td>Get all user notes</td>
<td>✅</td>
</tr>
<tr>
<td>POST</td>
<td>/api/notes</td>
<td>Create new note</td>
<td>✅</td>
</tr>
<tr>
<td>PUT</td>
<td>/api/notes/:id</td>
<td>Update note</td>
<td>✅</td>
</tr>
<tr>
<td>DELETE</td>
<td>/api/notes/:id</td>
<td>Delete note</td>
<td>✅</td>
</tr>
</table>

---

## 🔐 Security Features

| Feature | Implementation |
|---------|-----------------|
| **Password Hashing** | Bcryptjs with 10 salt rounds |
| **Authentication** | JWT tokens with 7-day expiry |
| **Rate Limiting** | 5 attempts/15 minutes on auth routes |
| **Input Validation** | Joi schema validation |
| **CORS Protection** | Configured allowed origins |
| **Error Messages** | Generic messages (no info leakage) |
| **Reset Tokens** | Hashed tokens with 1-hour expiry |
| **Cookie Management** | Secure HTTP-only cookies |

---

## 📝 Environment Variables

**Backend (.env)**
```env
PORT=3000
NODE_ENV=development
MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/note-app
JWT_SECRET=your_32_character_secret_key
BREVO_API_KEY=your_brevo_api_key
BREVO_SENDER_EMAIL=noreply@example.com
CLIENT_URL=http://localhost:5173
JWT_EXPIRE=7d
RESET_TOKEN_EXPIRE=1h
```

**Frontend (.env.local)**
```env
VITE_API_URL=http://localhost:3000/api
```

---

## 🧪 Testing Checklist

- [ ] Register new account
- [ ] Verify email from inbox
- [ ] Login with credentials
- [ ] Create a note
- [ ] Edit note
- [ ] Delete note
- [ ] Toggle dark mode
- [ ] Test forgot password
- [ ] Test rate limiting (6 wrong attempts)
- [ ] Logout & verify protection

---

## 🚀 Deployment

### Frontend (Vercel)
- Auto-deploy from GitHub
- Set `VITE_API_URL` to production backend URL
- Live: [note-app-omega-pied.vercel.app](https://note-app-omega-pied.vercel.app/)

### Backend (Render)
- Deploy Node.js application
- Set all environment variables
- Configure MongoDB Atlas connection

---

## 📚 Key Technologies Explained

| Technology | Purpose |
|------------|---------|
| **JWT** | Stateless token authentication |
| **Bcryptjs** | One-way password hashing with salt |
| **Mongoose** | MongoDB object modeling & validation |
| **Middleware** | Request/response processing chain |
| **CORS** | Allow cross-origin requests safely |
| **Nodemailer** | Send verification & reset emails |

---

## 🎯 Future Enhancements

- [ ] Collaborative note sharing
- [ ] Rich text editor
- [ ] Note tags & categories
- [ ] Full-text search
- [ ] PDF export
- [ ] Two-factor authentication (2FA)
- [ ] Social login (Google, GitHub)
- [ ] Mobile app (React Native)

---

## 🐛 Troubleshooting

| Issue | Solution |
|-------|----------|
| **Port 3000 in use** | `lsof -i :3000` → `kill -9 <PID>` |
| **MongoDB connection error** | Verify `MONGO_URI` in `.env` |
| **Email not sending** | Check Brevo API key & sender email |
| **Frontend API error** | Verify `VITE_API_URL` matches backend |
| **Token expired** | `localStorage.clear()` & re-login |

---

## 🤝 Contributing

```bash
# 1. Fork repository
# 2. Create feature branch
git checkout -b feature/YourFeature

# 3. Commit changes
git commit -m 'Add YourFeature'

# 4. Push to branch
git push origin feature/YourFeature

# 5. Open Pull Request
```

---

## 📄 License

This project is licensed under the **ISC License** - see LICENSE file for details.

---

## 👨‍💻 Author

<div align="center">

**Nitin Kumar**

[![GitHub](https://img.shields.io/badge/GitHub-@nitin01924-181717?style=for-the-badge&logo=github)](https://github.com/nitin01924)
[![Email](https://img.shields.io/badge/Email-nitin981275@gmail.com-EA4335?style=for-the-badge&logo=gmail)](mailto:nitin981275@gmail.com)
[![Portfolio](https://img.shields.io/badge/Portfolio-Note%20App-4285F4?style=for-the-badge)](https://note-app-omega-pied.vercel.app/)

</div>

---

<div align="center">

### ⭐ Support This Project

If you found this helpful, please give it a star! It helps others discover this project.

**[⬆ back to top](#-note-app---full-stack-mern-application)**

</div>
