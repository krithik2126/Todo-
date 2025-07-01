# TaskFlow - Real-Time Task Manager

## Overview

TaskFlow is a full-stack real-time task management application built with React and Express.js. The application enables users to authenticate via Google OAuth, manage tasks with real-time updates, and collaborate by sharing tasks with other users. The system uses WebSocket connections for live updates and provides a responsive user interface built with modern UI components.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite for development and production builds
- **Routing**: Wouter for client-side routing
- **State Management**: TanStack Query (React Query) for server state management
- **UI Components**: Radix UI primitives with shadcn/ui component library
- **Styling**: Tailwind CSS with CSS variables for theming
- **Form Handling**: React Hook Form with Zod validation

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Authentication**: Passport.js with Google OAuth 2.0 strategy
- **Session Management**: Express sessions with configurable storage
- **Real-time Communication**: WebSocket server using 'ws' library
- **API Design**: RESTful API endpoints with proper error handling
- **Input Validation**: Zod schemas for request validation

### Database Design
- **ORM**: Drizzle ORM for type-safe database operations
- **Database**: PostgreSQL (configured for Neon Database)
- **Schema Management**: Drizzle Kit for migrations and schema management
- **Storage Interface**: Abstracted storage layer supporting both in-memory (development) and PostgreSQL (production)

## Key Components

### Database Schema
- **Users Table**: Stores user information including Google OAuth data
- **Tasks Table**: Core task entity with status, priority, due dates, and assignment capabilities
- **Task Shares Table**: Manages task sharing permissions between users

### Authentication System
- Google OAuth 2.0 integration via Passport.js
- Session-based authentication with persistent login state
- Protected route middleware for API endpoints
- Automatic user creation on first login

### Real-time Features
- WebSocket server for live task updates
- Client-side WebSocket hooks for connection management
- Real-time notifications for task assignments, updates, and sharing
- Automatic reconnection handling

### Task Management
- CRUD operations for tasks with proper authorization
- Task filtering by status, priority, and date
- Task assignment to other users
- Task sharing with view/edit permissions
- Task statistics and dashboard analytics

### User Interface
- Responsive design supporting desktop and mobile
- Dark/light theme support
- Toast notifications for user feedback
- Modal dialogs for task creation and sharing
- Sidebar navigation with task statistics
- List and grid view modes for tasks

## Data Flow

1. **Authentication Flow**: Users authenticate via Google OAuth, creating/retrieving user records, establishing sessions
2. **Task Operations**: CRUD operations flow through REST API with real-time WebSocket notifications
3. **Real-time Updates**: WebSocket connections broadcast task changes to relevant users
4. **State Management**: React Query manages server state with automatic invalidation and refetching

## External Dependencies

### Core Dependencies
- **@neondatabase/serverless**: Neon Database PostgreSQL driver
- **passport & passport-google-oauth20**: Google OAuth authentication
- **ws**: WebSocket server implementation
- **drizzle-orm & drizzle-kit**: Database ORM and migration tools
- **@tanstack/react-query**: Server state management
- **@radix-ui/***: Headless UI component primitives
- **zod**: Schema validation library

### Development Tools
- **TypeScript**: Type safety across the application
- **Vite**: Build tool and development server
- **Tailwind CSS**: Utility-first CSS framework
- **PostCSS**: CSS processing with autoprefixer

## Deployment Strategy

### Build Process
- Frontend builds to static assets via Vite
- Backend compiles TypeScript to ESM modules via esbuild
- Single build output directory for unified deployment

### Environment Configuration
- Database connection via DATABASE_URL environment variable
- Google OAuth credentials via environment variables
- Session secret configuration for production security
- Configurable CORS and security settings

### Production Considerations
- Session storage can be configured for PostgreSQL persistence
- WebSocket server runs on same HTTP server instance
- Static file serving handled by Express in production
- Error handling and logging for production debugging

## Changelog

```
Changelog:
- July 01, 2025. Initial setup with React + Express architecture
- July 01, 2025. Implemented email/password authentication system
- July 01, 2025. Added PostgreSQL database with Drizzle ORM
- July 01, 2025. Created task management functionality (CRUD operations)
- July 01, 2025. Fixed task creation validation and date handling
- July 01, 2025. Implemented WebSocket for real-time updates
- July 01, 2025. Added task sharing functionality
- July 01, 2025. Created comprehensive dashboard with statistics
- July 01, 2025. Prepared for hackathon submission with README and architecture diagram
```

## User Preferences

```
Preferred communication style: Simple, everyday language.
```