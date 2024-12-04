nodemon index.js


# 🚀 React TypeScript Starter Kit

## 📋 Project Overview

A modern full-stack web application starter kit using React TypeScript, Vite, Shadcn UI, Tailwind CSS, and Node.js.

## 🚀 Technologies

- **Frontend**:
  - React 18
  - TypeScript
  - Vite
  - Shadcn UI
  - Tailwind CSS
  - React Router
  - Zod (Form Validation)
  - React Hook Form

- **Backend**:
  - Node.js
  - Express
  - TypeScript
  - MongoDB (optional)
  - JWT Authentication

## 📦 Prerequisites

- Node.js (v18+ recommended)
- npm or yarn
- Git

## 🔧 Project Setup

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/react-typescript-starter.git
cd react-typescript-starter
```

### 2. Install Dependencies

```bash
# Install frontend dependencies
cd frontend
npm install

# Install backend dependencies
cd ../backend
npm install
```

### 3. Environment Configuration

Create `.env` files in both `frontend` and `backend` directories:

**Frontend `.env`**:
```
VITE_API_URL=http://localhost:5000/api
```

**Backend `.env`**:
```
PORT=5000
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
```

### 4. Running the Application

**Development Mode**:

```bash
# Start frontend (Vite)
cd frontend
npm run dev

# Start backend (Node.js)
cd ../backend
npm run dev
```

**Production Build**:

```bash
# Build frontend
cd frontend
npm run build

# Build backend
cd ../backend
npm run build

# Start production server
npm start
```

## 📁 Project Structure

```
react-typescript-starter/
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── hooks/
│   │   ├── utils/
│   │   └── App.tsx
│   ├── vite.config.ts
│   └── tailwind.config.js
│
└── backend/
    ├── src/
    │   ├── controllers/
    │   ├── models/
    │   ├── routes/
    │   ├── middleware/
    │   └── server.ts
    └── tsconfig.json
```

## 🧪 Testing

```bash
# Frontend tests
cd frontend
npm run test

# Backend tests
cd ../backend
npm run test
```

## 🔒 Authentication

Includes JWT-based authentication with:
- Registration
- Login
- Protected routes
- Token refresh mechanism

## 📝 Shadcn UI Components

Pre-configured with Shadcn UI. Add components via:
```bash
npx shadcn-ui@latest add button
npx shadcn-ui@latest add input
```

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

## 🚨 Disclaimer

This is a starter kit. Customize and secure appropriately for production use.







# 🚀 React TypeScript Starter Kit

## Tech Stack

```typescript
const techStack = {
  frontend: {
    language: 'TypeScript',
    framework: 'React 18',
    bundler: 'Vite',
    styling: ['Tailwind CSS', 'Shadcn UI'],
    routing: 'React Router',
    validation: 'Zod',
    formHandling: 'React Hook Form'
  },
  backend: {
    language: 'TypeScript',
    runtime: 'Node.js',
    server: 'Express',
    database: 'MongoDB',
    authentication: 'JWT'
  }
}
```

## 🔧 Project Setup

### Frontend Configuration

```bash
# Install dependencies
npm create vite@latest frontend -- --template react-ts
cd frontend
npm install tailwindcss postcss autoprefixer shadcn-ui
npx tailwindcss init -p
```

### Tailwind CSS Config
```typescript
// tailwind.config.js
module.exports = {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: { extend: {} },
  plugins: [],
}
```

### Backend Setup

```bash
# Initialize Node.js TypeScript project
mkdir backend
cd backend
npm init -y
npm install express typescript @types/express @types/node
npx tsc --init
```

### Express Server Configuration
```typescript
// src/server.ts
import express from 'express';
import cors from 'cors';

const app = express();
const PORT = process.env.PORT || 5000;

app.use(cors());
app.use(express.json());

app.listen(PORT, () => {
  console.log(`Server running on port ${PORT}`);
});
```

## 💶 Scripts

```json
{
  "scripts": {
    "frontend:dev": "vite",
    "frontend:build": "tsc && vite build",
    "backend:dev": "ts-node-dev src/server.ts",
    "backend:build": "tsc",
    "start": "node dist/server.js"
  }
}
```

## 🔐 Authentication Middleware

```typescript
// src/middleware/authMiddleware.ts
import jwt from 'jsonwebtoken';

const authMiddleware = (req, res, next) => {
  const token = req.header('Authorization')?.replace('Bearer ', '');
  
  if (!token) {
    return res.status(401).json({ error: 'Authentication required' });
  }

  try {
    const decoded = jwt.verify(token, process.env.JWT_SECRET);
    req.user = decoded;
    next();
  } catch (error) {
    res.status(401).json({ error: 'Invalid token' });
  }
};

export default authMiddleware;
```

## 📁 Project Structure
```
project-root/
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   └── App.tsx
│   └── vite.config.ts
└── backend/
    ├── src/
    │   ├── routes/
    │   ├── controllers/
    │   └── server.ts
    └── tsconfig.json
```

## 🚀 Quick Start

```bash
# Clone repository
git clone https://github.com/yourusername/react-ts-starter.git

# Install dependencies
npm run install:all

# Run development servers
npm run dev
```

## 📝 Key Dependencies

```typescript
const keyDependencies = {
  frontend: [
    'react-router-dom',
    'shadcn-ui',
    'zod',
    'react-hook-form'
  ],
  backend: [
    'express',
    'mongoose',
    'jsonwebtoken',
    'bcryptjs'
  ],
  devDependencies: [
    'typescript',
    'vite',
    'tailwindcss',
    'ts-node-dev'
  ]
}
