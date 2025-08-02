# GEMS Task Manager - Frontend

A modern, responsive task management web application built with vanilla JavaScript, HTML, and CSS. Features a beautiful gradient interface with complete CRUD operations for tasks and comprehensive user management.

## 🚀 Live Demo

**Frontend**: [https://gg-alpha-fawn.vercel.app/](https://gg-alpha-fawn.vercel.app/)  
**Backend**: `https://gems-backend-whsr.onrender.com`

## ⚠️ Important Note

**Server Response Time**: Registration and login may take 15-20 seconds due to free tier server sleeping. This is normal behavior for the deployed backend service.

## 🎯 Features

### ✅ Task Management
- **Create Tasks**: Add new tasks with title, description, and due date
- **View Tasks**: Display all tasks with formatted dates (DD/MM/YYYY)
- **Edit Tasks**: Update task title, description, and due date
- **Delete Tasks**: Remove tasks with confirmation
- **Search by ID**: Find specific tasks using their unique ID
- **Task Details**: View complete task information including creation date

### ✅ User Management
- **User Registration**: Create new accounts with name, email, and password
- **User Login**: Secure authentication with JWT tokens
- **Profile Management**: View and update personal information
- **User Directory**: Browse all registered users
- **Profile Updates**: Modify name and email information

### ✅ Modern UI/UX
- **Responsive Design**: Works perfectly on desktop, tablet, and mobile
- **Beautiful Interface**: Gradient backgrounds and modern styling
- **Tab Navigation**: Organized sections for Tasks, Users, and Profile
- **Real-time Updates**: Auto-refresh tasks every 30 seconds
- **Error Handling**: Clear success and error messages
- **Loading States**: Visual feedback during operations

## 🚀 Deployment

This frontend is deployed on **Vercel**:
- **Live URL**: [https://gg-alpha-fawn.vercel.app/](https://gg-alpha-fawn.vercel.app/)
- **Platform**: Vercel (Static Site)
- **Auto-deploy**: Enabled on Git push

## 📱 How to Use

### Getting Started
1. **Visit the live application**: [https://gg-alpha-fawn.vercel.app/](https://gg-alpha-fawn.vercel.app/)
2. **Register a new account** (may take 15-20 seconds due to server sleeping)
3. **Login to your account** (may take 15-20 seconds due to server sleeping)
4. **Start managing your tasks!**

### Task Operations
- **Create Task**: Fill in title, description, and optional due date
- **View All Tasks**: See all your tasks with their details
- **Search Task**: Use the search box to find tasks by ID
- **Edit Task**: Click edit to modify task details
- **Delete Task**: Click delete with confirmation
- **View Details**: Click view to see complete task information

### User Features
- **Profile Tab**: View and update your personal information
- **Users Tab**: Browse all registered users
- **Update Profile**: Modify your name and email
- **View User Details**: Click on users to see their information

## 🎨 UI Features

### Design Elements
- **Gradient Background**: Beautiful purple-blue gradient
- **Card-based Layout**: Clean, organized interface
- **Responsive Grid**: Adapts to different screen sizes
- **Hover Effects**: Interactive buttons and elements
- **Color-coded Status**: Visual indicators for different states

### Navigation
- **Tab System**: Easy switching between Tasks, Users, and Profile
- **User Info Bar**: Shows current user and logout option
- **Form Validation**: Real-time input validation
- **Auto-refresh**: Tasks update automatically every 30 seconds

## 🔧 Technical Details

### Frontend Technologies
- **HTML5**: Semantic markup
- **CSS3**: Modern styling with gradients and animations
- **Vanilla JavaScript**: No frameworks, pure JS
- **Fetch API**: Modern HTTP requests
- **Local Storage**: Persistent authentication

### API Integration
- **Base URL**: `https://gems-backend-whsr.onrender.com/api`
- **Authentication**: JWT token-based
- **RESTful API**: Complete CRUD operations
- **Error Handling**: Comprehensive error management

### Browser Compatibility
- **Modern Browsers**: Chrome, Firefox, Safari, Edge
- **Mobile Support**: Responsive design for all devices
- **No Dependencies**: Works without any external libraries

## 📁 File Structure

```
frontend/
└── index.html          # Complete application (HTML + CSS + JS)
```

## 🛠️ Development

### Local Development
```bash
# Simply open index.html in any modern browser
# Or use a local server:
python -m http.server 8000
# Then visit: http://localhost:8000
```

### Customization
- **Colors**: Modify CSS variables in the `<style>` section
- **API URL**: Change `API_BASE` constant in JavaScript
- **Features**: Add new functionality in the JavaScript section

## 🔒 Security Features

- **JWT Authentication**: Secure token-based authentication
- **Input Validation**: Client-side and server-side validation
- **Error Handling**: Graceful error management
- **Session Management**: Automatic logout on token expiration

## 📞 Support

For issues or questions:
1. Check the browser console for error messages
2. Verify the backend API is accessible
3. Ensure you're using a modern browser
4. Check your internet connection

---

**Note**: This is a complete, self-contained frontend application. Just deploy `index.html` and you're ready to go!

