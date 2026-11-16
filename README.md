# ⚔️ Let's Code

> A real-time competitive coding platform where developers can battle head-to-head, solve coding problems, and compete through live WebSocket-powered matches.

---

# Overview

Let's Code is a full-stack competitive programming platform designed for real-time coding battles.

Users can:

* Join coding matches
* Compete against opponents live
* Submit and execute code
* Communicate through realtime socket events
* Track match activity and results

The project follows a service-oriented architecture with separate services for:

* API handling
* Realtime socket communication & matchmaking
* Code execution
* Frontend delivery

Let's Code focuses on realtime interaction, scalable backend communication, and modular deployment.

---

# Features

* User authentication and authorization
* Real-time coding battles
* WebSocket-powered live communication
* Online code execution
* Matchmaking system
* Multiple backend services
* Dockerized local development setup
* Responsive frontend UI
* REST API integration
* Redis integration for realtime systems

---

# Tech Stack

## Frontend

* React 19
* Vite
* Tailwind CSS
* Socket.IO Client
* Monaco Editor
* Yjs (Collaborative Editing)

## Backend

* Node.js
* Express.js
* Socket.IO
* BullMQ
* MongoDB
* Redis

## Infrastructure & Deployment

* Docker
* Docker Compose
* Vercel
* Render

---

# System Architecture

```txt
┌────────────────────┐
│      Frontend      │
│   React + Vite     │
└─────────┬──────────┘
          │
          │ HTTP / WebSocket
          │
┌─────────▼──────────┐
│    API Gateway     │
│     Express.js     │
└─────────┬──────────┘
          │
 ┌────────┴────────┐
 │                 │
 │                 │
▼▼                 ▼
Feature Service    Code Execution
(Socket.IO & Yjs)  Service (BullMQ)

          │
          ▼
     MongoDB
       Redis
```

---

# Project Structure

```txt
Let's Code/
│
├── frontend/                     # React + Vite frontend
│
├── backend/
│   ├── api-gateway/              # Reverse proxy & API Gateway
│   ├── code-runner-service/      # Code execution worker & queue
│   └── feature-service/          # Users, questions, chat, matchmaking, Yjs
│
├── docker-compose.yml
│
└── README.md
```

---

# Realtime Communication

Let's Code uses Socket.IO and Yjs for realtime interactions between players.

Realtime functionality includes:

* Match creation
* Match updates
* Live collaborative code editor synchronization
* Submission events
* In-arena real-time chat

The websocket layer allows players to stay synchronized during active coding sessions.

---

# Matchmaking

The platform includes a realtime matchmaking system that pairs users for coding battles.

Redis is used to support fast temporary state management and realtime coordination.

---

# Code Execution

Users can write and submit code directly from the browser.

The backend execution service:

* Receives submissions
* Enqueues tasks in BullMQ
* Processes execution requests
* Returns execution results
* Handles multiple programming languages

---

# Local Development Setup

## Prerequisites

* Node.js (v18+ recommended)
* Docker & Docker Compose (optional for containerized setup)
* MongoDB
* Redis

---

# Installation

## Clone Repository

```bash
git clone https://github.com/astitva1216/Let's Code.git
cd Let's Code
```

---

# Install Dependencies

### 1. Frontend

```bash
cd frontend
npm install
```

### 2. API Gateway

```bash
cd ../backend/api-gateway
npm install
```

### 3. Code Runner Service

```bash
cd ../code-runner-service
npm install
```

### 4. Feature Service

```bash
cd ../feature-service
npm install
```

---

# Run With Docker

```bash
docker-compose up --build
```

---

# Run Locally (Without Docker)

### Run Frontend

```bash
cd frontend
npm run dev
```

### Run API Gateway

```bash
cd backend/api-gateway
npm run dev
```

### Run Code Runner Service

```bash
cd backend/code-runner-service
npm run dev
```

### Run Feature Service

```bash
cd backend/feature-service
npm run dev
```

---

# Environment Variables

Example environment variables:

```env
PORT=8000
MONGODB_URI=your_mongodb_uri
REDIS_HOST=localhost
REDIS_PORT=6379
JWT_SECRET=your_jwt_secret
CLIENT_URL=http://localhost:5173
```

---

# Deployment

## Frontend

* Vercel

## Backend Services

* Render

## Local Infrastructure

* Docker Compose

---

# Future Improvements

* Ranked matchmaking
* Leaderboard system
* Match replay system
* Contest mode
* Team battles
* AI-assisted problem recommendations
* Improved analytics dashboard

---

# Author

**Astitva Garg**
* GitHub: [@astitva1216](https://github.com/astitva1216)
* Email: [astitva1216@gmail.com](mailto:astitva1216@gmail.com)
