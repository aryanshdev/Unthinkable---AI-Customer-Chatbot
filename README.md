# Unthinkable AI Customer Support ChatBot

> For Original Work Record Visit https://github.com/aryanshdev/Unthinkable-Frontend For Frontend And https://github.com/aryanshdev/Unthinkable-Backend For Backend
## Table of Contents

- [About](#about)
	- [Demo Video](#demo-video)
- [Getting Started](#getting-started)
	- [Requirements To Run This Project](#requirements-to-run-this-project)
	- [Using The Project](#using-the-project)
		- [Start Both Frontend & Backend Together (Recommended for Development)](#1-start-both-frontend--backend-together-recommended-for-development)
		- [Start Only Backend or Only Frontend (Separate)](#2-start-only-backend-or-only-frontend-separate)
- [Working](#working)
	- [System Architecture](#system-architecture)
	- [Frontend](#frontend)
	- [Backend](#backend)

## About

This is a complete working prototype of an AI Integrated Customer Support Chatbot made by **Aryansh Gupta** (_aryanshdev_) with registration number - **22BCE10404**.

This ChatBot leverages a **Knowledge Base** of publicly available information about Unthinkable Solutions and is completely **Context-Aware**. It has **Persistence** and can store all previous chats of a user. It provides **Escalation management** with suitable CTAs (Call-To-Action).

You Can Try It Out At Ourself: [https://unthinkable-chatbot.vercel.app](https://unthinkable-chatbot.vercel.app/)

#### Demo Video
[You Can Also Watch Here](https://drive.google.com/file/d/1ACEJ4GlD2du80Z9_kIbrOpGP_TTtQlKr/view)


<iframe src="https://drive.google.com/file/d/1ACEJ4GlD2du80Z9_kIbrOpGP_TTtQlKr/preview" width="495" height="270"></iframe>

## Getting Started

- You can try a hosted version at : [https://unthinkable-chatbot.vercel.app/](https://unthinkable-chatbot.vercel.app/)

- OR you can run it yourself by following the steps below.

#### Requirements To Run This Project

- NodeJS
- PostgreSQL (Local or Hosted, any one works)

## Using The Project

You can run the **frontend** and **backend** either together (in parallel) or separately. Follow the instructions below for both approaches.

You will need to create a `.env` file in backend directory with following keys and secrets -
- GROQ_API
- GOOGLE_CLIENT_ID
- GOOGLE_CLIENT_SECRET
- DATABASE_URL
- JWT_SIGN

### 1. Start Both Frontend & Backend Together (Recommended for Development)

#### Using Two Terminals

Open two terminal windows/tabs:

**Terminal 1: Start Backend**

```bash
cd Backend
npm install             # Only needed once
npx prisma generate     # Only needed once
npx prisma migrate dev  # Only needed once
node server.js
```

**Terminal 2: Start Frontend**

```bash
cd frontend
npm install   # Only needed once
npm run dev
```

The backend will run on `http://localhost:10000`, and the frontend on `http://localhost:3000` by default.

Open `http://localhost:3000` on your browser to use the app

### 2. Start Only Backend or Only Frontend (Separate)

#### Start Backend Only

```bash
cd Backend
npm install
node server.js
```

#### Start Frontend Only

```bash
cd frontend
npm install
npm run dev
```

---

## Working

### System Architecture

<img width="1920" height="583" alt="System Architecture" src="https://github.com/user-attachments/assets/40d20789-93c0-4da5-b6f2-d1fe23bcdd6e" />


### Frontend

> [Original Repo At : https://github.com/aryanshdev/Unthinkable-Frontend](https://github.com/aryanshdev/Unthinkable-Frontend) <br> You Can Check The Original Commit History There

The frontend is constructed using **Next.js**, with **NextNavigation** for handling routing. State management and UI logic are managed with **vanilla JavaScript**, utilizing React **Contexts** and **Hooks**. Real-time communication is enabled through the **Socket.io Client** for client-side WebSocket connections.

### Backend

> [Original Repo At : https://github.com/aryanshdev/Unthinkable-Backend](https://github.com/aryanshdev/Unthinkable-Backend) <br> You Can Check The Original Commit History There

The backend is built on the **Node.js** runtime, using the **Express.js** framework. Key technologies include:

- **Database**: `PostgreSQL` serves as the primary database.
- **ORM**: `Prisma` is used for object-relational mapping.
- **Authentication**: User sign-in is handled by `Passport Google OAuth`.
- **Authorization**: `JWT` are used for authorization and access control.
- **Real-time Communication**: `Socket.io` used for realtime WebSocket communication.
- **Scalability**: `Kafka` is integrated to manage and scale database write operations efficiently.
- **AI Integration**: The `Groq SDK` is used to Integrate the AI Inference Engine.
