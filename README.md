# Collaboard Backend

Backend API server for Collaboard collaborative whiteboard application.

## Tech Stack

- **Node.js** with Express
- **TypeScript** for type safety
- **MongoDB** with Mongoose
- **Socket.IO** for real-time WebSocket communication
- **JWT** for authentication

## Features

- RESTful API for boards, elements, and user management
- Real-time WebSocket collaboration
- JWT-based authentication
- MongoDB data persistence
- Rate limiting and security middleware

## Getting Started

### Prerequisites

- Node.js 18+
- MongoDB (local or MongoDB Atlas)

### Installation

1. **Install dependencies**:
   ```bash
   npm install
   ```

2. **Set up environment variables**:
   ```bash
   cp env.example .env
   ```
   
   Edit `.env` and configure:
   ```env
   MONGODB_URI=mongodb://localhost:27017/collaboard
   JWT_SECRET=your-secret-key-change-in-production
   PORT=3001
   CORS_ORIGIN=http://localhost:5173
   ```

3. **Build the project**:
   ```bash
   npm run build
   ```

4. **Start the server**:
   ```bash
   npm start
   ```

   Or for development:
   ```bash
   npm run dev
   ```

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/me` - Get current user
- `PUT /api/auth/profile` - Update user profile

### Boards
- `GET /api/boards` - Get all boards for user
- `GET /api/boards/:id` - Get single board with elements
- `POST /api/boards` - Create new board
- `PUT /api/boards/:id` - Update board
- `DELETE /api/boards/:id` - Delete board
- `POST /api/boards/:id/collaborators` - Add collaborator
- `DELETE /api/boards/:id/collaborators/:userId` - Remove collaborator

### Elements
- `GET /api/elements/board/:boardId` - Get elements for board
- `POST /api/elements` - Create element
- `POST /api/elements/batch-save` - Batch save elements
- `PUT /api/elements/:id` - Update element
- `DELETE /api/elements/:id` - Delete element

## WebSocket Events

See [WebSocket Implementation Documentation](../docs/WEBSOCKET_IMPLEMENTATION.md) for detailed Socket.IO event documentation.

## Deployment

See [Backend Deployment Guide](../docs/BACKEND_DEPLOYMENT.md) for deployment instructions to:
- Render
- Railway
- Fly.io
- DigitalOcean
- And more

## Scripts

- `npm run dev` - Start development server with hot reload
- `npm run build` - Build TypeScript to JavaScript
- `npm start` - Start production server
- `npm test` - Run tests
- `npm run delete-all-boards` - Delete all boards from database (development)

## Environment Variables

See `env.example` for all available environment variables.

## License

MIT

