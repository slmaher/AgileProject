# AgileProject

Project containing three parts:
- `api` — Express API server (Prisma + MongoDB connection)
- `client` — React + Vite frontend
- `socket` — Socket.IO server for real-time messaging

**Overview**

The API serves REST endpoints on port 8800 and requires environment variables for the database, JWT secret, and the client URL. The client runs with Vite (default port 5174). The socket server listens on port 4000 and accepts connections from the client.

---

## What this Project Does

This project is a small real-estate marketplace and messaging platform. Key features include:

- User registration and authentication using JWT.
- Profile management.
- Create, edit, and delete property listings.
- Upload images and rich-text descriptions for properties.
- Browse listings with filtering, search, and map views.
- View detailed property information.
- Real-time chat and messaging between users via Socket.IO.

---

## Project Structure

```text
AgileProject/
├── api/       # Express API + Prisma + MongoDB
├── client/    # React + Vite frontend
└── socket/    # Socket.IO real-time server
```

---

## Tech Stack

### Backend (`api`)
- Express.js
- Prisma ORM
- MongoDB
- JWT Authentication

### Frontend (`client`)
- React
- Vite

### Real-Time Communication (`socket`)
- Socket.IO

---

## Prerequisites

Before running the project, make sure you have:

- Node.js (version 18 or later)
- npm or Yarn
- Access to a MongoDB database

---

## Environment Variables

Create a file named `api/.env` and add the following variables:

```env
DATABASE_URL="mongodb+srv://<username>:<password>@cluster0.example.mongodb.net/estate?retryWrites=true&w=majority&appName=Cluster0"
JWT_SECRET_KEY=your_jwt_secret_here
CLIENT_URL=http://localhost:5174
```

### Variable Description

| Variable | Description |
|--------|--------|
| `DATABASE_URL` | MongoDB connection string |
| `JWT_SECRET_KEY` | Secret key used to sign JWT tokens |
| `CLIENT_URL` | Frontend URL allowed by CORS |

> **Important:** Never commit `.env` files to version control. If credentials are exposed, rotate them immediately.

---

## Installation

Install dependencies for each service:

```bash
# API
cd api
npm install

# Client
cd ../client
npm install

# Socket Server
cd ../socket
npm install
```

---

## Running the Project (Development)

Start each service in a separate terminal.

### API Server

Runs on **http://localhost:8800**

```bash
cd api
node app.js

# Or with automatic reload
npx nodemon app.js
```

### Socket Server

Runs on **http://localhost:4000**

```bash
cd socket
node app.js

# Or with automatic reload
npx nodemon app.js
```

### Client Application

Runs on **http://localhost:5174**

```bash
cd client
npm run dev
```

---

## Quick Verification

- API Test Endpoint: `http://localhost:8800/api/test`
- Client Application: `http://localhost:5174`
- Socket Server: `http://localhost:4000`

---

## API Modules

The API provides endpoints for:

- Authentication
- Users
- Property Posts
- Chats
- Messages

---

## Development Notes

- Ensure the MongoDB connection string is valid before starting the API.
- Run all three services simultaneously for full functionality.
- The socket server handles real-time chat and online user tracking.
- Vite may use a different port if `5174` is already in use.
