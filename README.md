# RetroFlow - Backend API & Real-time Server

RetroFlow is a collaborative Agile Sprint & Retrospective management platform. This repository contains the backend REST API and WebSocket real-time server built with Node.js, Express, MongoDB, and Socket.io.

## 🚀 Tech Stack

- **Runtime**: [Node.js](https://nodejs.org/)
- **Framework**: [Express.js](https://expressjs.com/)
- **Database**: [MongoDB Atlas](https://www.mongodb.com/atlas) with [Mongoose](https://mongoosejs.com/)
- **Real-time Sync**: [Socket.io](https://socket.io/)
- **Authentication**: JWT & Firebase Admin SDK
- **Email Service**: Brevo (Sendinblue) Transactional API

## 📁 Project Structure

```
├── config/              # Database, environment, and admin configuration
├── controllers/         # Request handling & HTTP response logic
│   ├── auth.controller.js
│   ├── members.controller.js
│   ├── project.controller.js
│   ├── retro.controller.js
│   ├── scorecard.controller.js
│   └── settings.controller.js
├── middlewares/         # Auth, validation, error handler, rate limiters
├── models/              # Mongoose schemas (User, Project, RetroBoard, Scorecard)
├── routes/              # Express API endpoints routing
├── services/            # Core business logic (projects, sprints, retro, email)
├── sockets/             # Real-time WebSocket handlers for live retro boards
├── utils/               # ApiError, ApiResponse, tokens, roles
├── validations/         # Input validation schemas
├── server.js            # Main entry point & Socket.io server bootstrap
└── package.json
```

## 🛠️ Getting Started

### Prerequisites

- Node.js 18+ or 20+
- MongoDB instance (MongoDB Atlas or local MongoDB)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/gopalgohil/RetroFlow_Backend.git
cd RetroFlow_Backend
```

2. Install dependencies:
```bash
npm install
```

3. Configure environment variables:
Create a `.env` file from `.env.example`:
```bash
cp .env.example .env
```
Fill in your configuration:
- `PORT`: Server port (default: 5000)
- `MONGODB_URI`: MongoDB connection string
- `CLIENT_URL`: URL of the frontend app (e.g. `http://localhost:3000`)
- `JWT_SECRET`: Secret key for JWT signing
- `BREVO_API_KEY`: API key for email notifications
- `SUPER_ADMIN_EMAIL`: Initial super admin email

4. Start development server:
```bash
npm run dev
# or
npm start
```

The server will start on [http://localhost:5000](http://localhost:5000).

## 📡 Key Features

- **Sprint & Backlog Management**: Create projects, plan sprints, manage backlog items, track velocity, complete sprints with automatic rollover of unfinished tasks.
- **Interactive Retrospectives**: Live column-based boards (Went Well, To Improve, Action Items) with real-time socket synchronization.
- **Export Action Items**: Route retro action items directly to target sprints or product backlog.
- **Access Control & Approvals**: Multi-tenant workspace approvals, role-based access control (Super Admin, Manager, Contributor).
- **Team Scoreboards & Analytics**: Track sprint completion, team contributions, and retro metrics over time.
