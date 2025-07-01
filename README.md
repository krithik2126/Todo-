# TaskFlow - Real-Time Task Manager

A collaborative real-time task management platform built for seamless productivity and team collaboration.

## 🚀 Live Demo

[View Live Application](https://your-app-domain.replit.app) *(Will be updated after deployment)*

## 📹 Demo Video

[Watch Demo Video](https://your-loom-link-here) *(Will be updated with actual demo)*

## 🏗️ Architecture Overview

TaskFlow follows a modern full-stack architecture designed for scalability and real-time collaboration:

### Tech Stack
- **Frontend**: React 18 + TypeScript + Vite
- **Backend**: Node.js + Express.js
- **Database**: PostgreSQL with Drizzle ORM
- **Authentication**: Email/Password with bcrypt
- **Real-time**: WebSocket connections
- **UI**: Radix UI + shadcn/ui + Tailwind CSS
- **State Management**: TanStack Query (React Query)

### System Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   React Client  │◄──►│  Express Server │◄──►│   PostgreSQL    │
│                 │    │                 │    │    Database     │
│ • UI Components │    │ • REST API      │    │ • User Data     │
│ • WebSocket     │    │ • WebSocket     │    │ • Tasks         │
│ • State Mgmt    │    │ • Auth Layer    │    │ • Sharing       │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

## ✨ Features

### Core Functionality
- **User Authentication**: Secure email/password registration and login
- **Task Management**: Create, edit, delete, and organize tasks
- **Real-time Updates**: Live synchronization across all connected users
- **Task Sharing**: Collaborate by sharing tasks with team members
- **Status Tracking**: Todo, In Progress, and Completed task states
- **Priority Levels**: Low, Medium, and High priority classification
- **Due Date Management**: Set and track task deadlines
- **Task Assignment**: Assign tasks to specific team members

### User Interface
- **Responsive Design**: Works seamlessly on desktop and mobile
- **Dark/Light Theme**: Toggle between themes for user preference
- **Dashboard Analytics**: Visual overview of task statistics
- **List & Grid Views**: Multiple ways to view and organize tasks
- **Real-time Notifications**: Instant updates when tasks change
- **Filter & Search**: Find tasks quickly with advanced filtering

### Technical Features
- **Type Safety**: Full TypeScript implementation
- **Real-time Sync**: WebSocket-based live updates
- **Session Management**: Persistent user sessions
- **Data Validation**: Client and server-side validation
- **Error Handling**: Comprehensive error management
- **Performance**: Optimized queries and caching

## 🔧 Setup Instructions

### Prerequisites
- Node.js 18+ installed
- PostgreSQL database (we recommend Neon Database)
- Git for version control

### Environment Variables
Create a `.env` file in the root directory:

```env
DATABASE_URL=your_postgresql_connection_string
SESSION_SECRET=your_secure_session_secret_key
NODE_ENV=development
```

### Installation Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/taskflow.git
   cd taskflow
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up the database**
   ```bash
   npm run db:push
   ```

4. **Start the development server**
   ```bash
   npm run dev
   ```

5. **Access the application**
   Open your browser to `http://localhost:5000`

## 📊 Database Schema

### Users Table
- `id`: Primary key
- `email`: Unique email address
- `name`: User's display name
- `password`: Hashed password (bcrypt)
- `avatar`: Optional profile image URL
- `createdAt`, `updatedAt`: Timestamps

### Tasks Table
- `id`: Primary key
- `title`: Task title
- `description`: Optional task description
- `status`: todo | in-progress | completed
- `priority`: low | medium | high
- `dueDate`: Optional due date
- `userId`: Task creator (foreign key)
- `assignedTo`: Optional assignee (foreign key)
- `createdAt`, `updatedAt`: Timestamps

### Task Shares Table
- `id`: Primary key
- `taskId`: Reference to shared task
- `userId`: User with access to task
- `permission`: read | write permissions
- `createdAt`: Share timestamp

## 🎯 Key Assumptions

Based on the hackathon requirements, we made the following assumptions:

1. **Authentication Method**: Implemented email/password authentication instead of OAuth for simplicity and broader accessibility
2. **Real-time Requirements**: Assumed all task operations should sync in real-time across all connected users
3. **Collaboration Model**: Tasks can be shared with specific users rather than public/team-based sharing
4. **Data Persistence**: Assumed production deployment requires persistent PostgreSQL storage
5. **UI/UX Preferences**: Focused on modern, clean interface with dark/light theme support
6. **Performance**: Optimized for small to medium teams (up to 100 concurrent users)
7. **Browser Support**: Targeted modern browsers with WebSocket support

## 🚀 Deployment

This application is designed to be deployed on Replit with the following considerations:

### Production Setup
1. **Database**: Configure PostgreSQL connection string
2. **Session Storage**: Uses database-backed sessions for persistence
3. **Environment**: Set `NODE_ENV=production`
4. **Port Binding**: Configured for `0.0.0.0` binding

### Build Process
- Frontend assets compiled with Vite
- TypeScript compiled to ESM modules
- Single server serves both API and static files

## 🔍 Development Highlights

### Code Quality
- **Modular Architecture**: Separated concerns with clear boundaries
- **Type Safety**: Comprehensive TypeScript coverage
- **Error Handling**: Robust error management and user feedback
- **Validation**: Client and server-side input validation
- **Security**: Password hashing, session management, CORS protection

### Performance Optimizations
- **Query Optimization**: Efficient database queries with Drizzle ORM
- **Caching**: React Query for intelligent data caching
- **WebSocket Management**: Automatic reconnection and connection pooling
- **Bundle Optimization**: Tree-shaking and code splitting with Vite

## 📈 Future Enhancements

- [ ] Team/Organization management
- [ ] File attachments for tasks
- [ ] Task templates and automation
- [ ] Advanced filtering and search
- [ ] Mobile app development
- [ ] Integration with external tools (Slack, GitHub, etc.)
- [ ] Advanced analytics and reporting
- [ ] Task dependencies and project management

## 🤝 Contributing

This project was built as part of a hackathon. For questions or suggestions, please reach out to the development team.

## 📄 License

This project is open source and available under the MIT License.

---

**This project is a part of a hackathon run by https://www.katomaran.com**