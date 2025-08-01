# GEMS Task Manager

A complete task management system with backend API and frontend interface.

## 🚀 Deployment Guide

### Frontend Deployment (index.html)

#### Option 1: GitHub Pages (Recommended)
1. **Create a GitHub repository**
2. **Upload your files**:
   - `index.html`
   - `api.md`
   - `README.md`
3. **Enable GitHub Pages**:
   - Go to Settings → Pages
   - Select "Deploy from a branch"
   - Choose `main` branch
   - Save
4. **Your site will be available at**: `https://yourusername.github.io/repository-name`

#### Option 2: Netlify (Free)
1. **Go to [netlify.com](https://netlify.com)**
2. **Drag and drop** your `index.html` file
3. **Your site will be live instantly** with a URL like: `https://random-name.netlify.app`

#### Option 3: Vercel (Free)
1. **Go to [vercel.com](https://vercel.com)**
2. **Import your GitHub repository** or upload files
3. **Deploy automatically**

#### Option 4: Render (Free)
1. **Go to [render.com](https://render.com)**
2. **Create a new Static Site**
3. **Upload your files**
4. **Deploy**

### Backend Deployment
Your backend is already deployed on Render at: `https://gems-backend-whsr.onrender.com`

## 📁 Project Structure

```
gems-backend/
├── index.html          # Frontend (deploy this)
├── api.md             # API Documentation
├── server.js          # Backend server
├── config/
│   └── db.js         # Database configuration
├── controllers/
│   ├── authController.js
│   └── taskController.js
├── middleware/
│   └── authMiddleware.js
├── models/
│   ├── Task.js
│   └── User.js
├── routes/
│   ├── auth.js
│   └── task.js
└── package.json
```

## 🔧 Configuration

### Frontend Configuration
The frontend is already configured to use your deployed backend:
- **API Base URL**: `https://gems-backend-whsr.onrender.com/api`
- **Authentication**: JWT tokens
- **Features**: Complete CRUD operations for tasks and users

### Backend Configuration
- **Database**: MongoDB
- **Authentication**: JWT
- **Deployment**: Render
- **Environment Variables**: Set in Render dashboard

## 🎯 Quick Start

1. **Deploy Frontend**: Choose any option above
2. **Access your app**: Open the deployed URL
3. **Register/Login**: Create an account
4. **Start managing tasks**: Use all features

## 📱 Features

### ✅ Complete Task Management
- Create, Read, Update, Delete tasks
- Search tasks by ID
- Date formatting (DD/MM/YYYY)
- Real-time updates

### ✅ User Management
- User registration and login
- Profile management
- View all users
- Update user information

### ✅ Modern UI/UX
- Responsive design
- Beautiful gradient interface
- Tab-based navigation
- Error handling and success messages

## 🔗 API Documentation

See `api.md` for complete API documentation including:
- All endpoints
- Request/response formats
- Authentication requirements
- Error responses

## 🛠️ Development

### Local Development
```bash
# Backend
npm install
npm start

# Frontend
# Just open index.html in browser
```

### Environment Variables
```env
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
PORT=5000
```

## 📞 Support

For any issues or questions, check the API documentation or review the code comments.

---

**Note**: The frontend is completely self-contained in `index.html` and ready for deployment!

