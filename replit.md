# VIT-AP Study Hub

## Overview

VIT-AP Study Hub is a full-stack web application designed for students to browse, search, and access academic study materials including question papers, study notes, and lab manuals. The application features a modern React frontend with TypeScript, Express.js backend, and PostgreSQL database with Drizzle ORM.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite for fast development and optimized builds
- **Routing**: Wouter for lightweight client-side routing
- **UI Framework**: Shadcn/UI components built on Radix UI primitives
- **Styling**: Tailwind CSS with custom design system
- **State Management**: TanStack Query (React Query) for server state management
- **Forms**: React Hook Form with Zod validation

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **Runtime**: Node.js with ES modules
- **API Style**: RESTful API design
- **Database**: PostgreSQL with Drizzle ORM
- **Session Management**: Express sessions with PostgreSQL store
- **Development**: Hot reload with Vite middleware in development

### Database Schema
The application uses a single main table `study_materials` with the following structure:
- Material metadata (title, subject, department, semester)
- Academic information (academic year, content type, exam type)
- File management (file URLs, download counts)
- User interactions (bookmarks, tags)
- Timestamps for tracking uploads

## Key Components

### Data Storage Layer
- **Primary Storage**: In-memory storage class (MemStorage) for development with seed data
- **Production Ready**: Drizzle ORM configuration for PostgreSQL
- **Schema**: Type-safe database schema with Zod validation
- **Migrations**: Drizzle migrations system for database versioning

### API Endpoints
- `GET /api/materials` - Fetch study materials with advanced filtering
- `GET /api/materials/:id` - Get specific material details
- `POST /api/materials/:id/download` - Increment download counter and track usage

### Frontend Features
- **Material Browser**: Grid layout with filtering and pagination
- **Advanced Search**: Multi-criteria filtering (department, semester, content type, academic year)
- **Responsive Design**: Mobile-first approach with collapsible sidebar
- **Material Cards**: Rich preview cards with metadata and actions
- **Bookmark System**: User can bookmark favorite materials

### UI Components
- Comprehensive component library based on Shadcn/UI
- Custom VIT-AP branding with blue primary color scheme
- Responsive navigation with mobile hamburger menu
- Pagination controls for large datasets
- Loading states and error handling

## Data Flow

1. **Material Discovery**: Users browse materials through the main interface
2. **Filtering**: Advanced filters narrow down results by department, semester, content type
3. **Search**: Real-time search across material titles and subjects
4. **Material Access**: Users can view details and download materials
5. **Analytics**: Download counts track popular materials
6. **Personalization**: Bookmark system for user favorites

## External Dependencies

### Core Dependencies
- **@neondatabase/serverless**: Neon database driver for PostgreSQL
- **drizzle-orm**: Type-safe ORM for database operations
- **@tanstack/react-query**: Server state management
- **@radix-ui/***: Headless UI components for accessibility
- **tailwindcss**: Utility-first CSS framework
- **zod**: Schema validation library

### Development Tools
- **vite**: Build tool and development server
- **tsx**: TypeScript execution for Node.js
- **esbuild**: Fast JavaScript bundler for production
- **@replit/vite-plugin-runtime-error-modal**: Development error handling

## Deployment Strategy

### Development
- Vite dev server with HMR for frontend
- Express server with TypeScript compilation via tsx
- In-memory storage for rapid prototyping
- Environment variables for database configuration

### Production Build
- Frontend: Vite builds optimized static assets
- Backend: esbuild bundles Node.js application
- Database: Drizzle migrations for schema management
- Deployment: Single process serving both API and static files

### Configuration
- TypeScript configuration supports both client and server code
- Path mapping for clean imports (`@/` for client, `@shared/` for shared types)
- PostCSS with Tailwind CSS processing
- Environment-based configuration for database connections

The application is designed for easy deployment on platforms like Replit, with automatic database provisioning and streamlined build processes.