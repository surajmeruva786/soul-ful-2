# SoulFul Trips Project Guide

## Overview

SoulFul Trips is a travel website showcasing various destinations, travel packages, and inspiring travel content. The application is built as a fullstack JavaScript application with:

- React frontend with Tailwind CSS and Shadcn/UI components
- Express backend API 
- Drizzle ORM for database management
- TypeScript throughout the entire codebase
- PostgreSQL database (to be integrated)

The site features a modern, responsive design with various sections including popular destinations, travel packages, testimonials, and a photo gallery.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture

The frontend is built with React and follows a component-based architecture:

1. **Pages**: Main route components that compose various UI sections
2. **Components**: Reusable UI elements organized by feature and purpose
   - Section components (e.g., HeroSection, DestinationsSection)
   - UI components (from Shadcn/UI library)
3. **Data Management**: 
   - Static data files for destinations, testimonials, etc.
   - React Query for potential API data fetching
4. **Styling**: Tailwind CSS with custom theme configuration

### Backend Architecture

The backend is a lightweight Express server with:

1. **API Routes**: Simple RESTful endpoints
2. **Storage Layer**: Currently using in-memory storage, with infrastructure ready for PostgreSQL
3. **Database Schema**: Defined with Drizzle ORM

### Database Architecture

The application is set up to use PostgreSQL with Drizzle ORM:

1. **Schema Definition**: Located in shared/schema.ts
2. **ORM Configuration**: Configured in drizzle.config.ts
3. **Current State**: PostgreSQL module is included but not fully integrated yet

## Key Components

### Frontend Components

1. **Pages**:
   - Home: Main landing page with all sections
   - NotFound: 404 error page

2. **Section Components**:
   - Header: Navigation bar
   - HeroSection: Main banner with call-to-action
   - DestinationsSection: Featured travel destinations
   - PackagesSection: Travel package offerings
   - TestimonialsSection: Customer reviews
   - GallerySection: Travel photos gallery
   - CTASection: Call-to-action form
   - Footer: Site footer with links

3. **UI Components**:
   - Comprehensive set of Shadcn/UI components (buttons, cards, forms, etc.)
   - Custom animations using Framer Motion

### Backend Components

1. **Server Setup**: Main Express server configuration in server/index.ts
2. **Routes**: API endpoints defined in server/routes.ts
3. **Storage**: Data management interface in server/storage.ts
4. **Development Tools**: Vite dev server integration in server/vite.ts

### Shared Components

1. **Database Schema**: User model defined in shared/schema.ts
2. **TypeScript Types**: Shared types for frontend and backend

## Data Flow

1. **Frontend Data Loading**:
   - Currently using static data files in client/src/data/
   - Ready for API integration with React Query setup

2. **API Communication**:
   - Frontend -> Backend: Uses fetch API with JSON data
   - Error handling and response processing via apiRequest utility

3. **Database Operations**:
   - Storage interface defines CRUD operations
   - Currently using in-memory storage implementation
   - Prepared for PostgreSQL integration

## External Dependencies

### Frontend Dependencies

1. **UI Framework**: React with TypeScript
2. **Routing**: Wouter (lightweight alternative to React Router)
3. **Styling**: Tailwind CSS
4. **UI Components**: Shadcn/UI with Radix UI primitives
5. **Animation**: Framer Motion
6. **Data Fetching**: TanStack React Query
7. **Icons**: Lucide React

### Backend Dependencies

1. **Server**: Express
2. **Database ORM**: Drizzle ORM
3. **Database Client**: Ready for NeonDB Serverless PostgreSQL
4. **Validation**: Zod (via drizzle-zod)

## Deployment Strategy

The application is configured for deployment on Replit:

1. **Build Process**:
   - Frontend: Vite builds static assets
   - Backend: esbuild bundles server code
   - Combined output in /dist directory

2. **Development Mode**:
   - `npm run dev` starts both frontend and backend in development mode
   - Uses Vite middleware for hot module replacement

3. **Production Mode**:
   - `npm run build` creates optimized production build
   - `npm run start` runs the production server

4. **Database Strategy**:
   - Ready for PostgreSQL integration via the .replit configuration
   - Needs DATABASE_URL environment variable to be set

## Next Steps for Development

1. **Database Integration**:
   - Complete PostgreSQL setup
   - Implement Drizzle ORM queries for user data

2. **Authentication**:
   - Implement user authentication system
   - Add protected routes for user accounts

3. **Backend Functionality**:
   - Develop API endpoints for travel packages, bookings, etc.
   - Replace static data with dynamic database content

4. **Frontend Enhancements**:
   - Add more interactive features
   - Implement user dashboard and booking system

5. **Testing**:
   - Add unit and integration tests