# BW-AI-Challenge-2-Election-Process-Education
Build with AI Challenge 2

# Election Process Education Assistant

A full-stack, AI-powered interactive web application designed to help users understand the election process in a simple, structured, and engaging way.

## Features

1. **AI Chat Assistant**: Context-aware chatbot for instant query resolution.
2. **Guided Learning Flow**: Step-by-step modules (Voter Registration, Nomination, Campaigning, Voting, Results).
3. **Interactive Timeline**: Visual timeline of the entire process.
4. **Quiz System**: Gamified quiz with instant feedback to test knowledge.

## Tech Stack

- **Frontend**: Next.js 15, React 19, Tailwind CSS, Framer Motion, Lucide Icons.
- **Backend**: Node.js, Express, TypeScript, Nodemon.
- **Design System**: Stitch (Modern, clean, blue/white aesthetics, highly responsive).

## Folder Structure

```
c:\PromptWars Online-1\
├── frontend/             # Next.js Application
│   ├── src/app/          # App router pages (chat, learn, quiz, timeline)
│   ├── src/components/   # Reusable components (Navbar)
│   └── public/           # Static assets
└── backend/              # Node.js Express Server
    ├── src/              
    │   ├── server.ts     # Main entry point & Express config
    │   └── routes/       # API Routes (chat.ts)
    └── package.json      # Backend dependencies & scripts
```

## Setup Instructions

### Environment Variables

Before running the application, you must set up the environment variables. 
Copy the `.env.example` files to `.env` in both the `frontend` and `backend` directories.

**Frontend (`frontend/.env`):**
```env
NEXT_PUBLIC_DEMO_EMAIL=user@demo.com
NEXT_PUBLIC_DEMO_PASSWORD=password123
NEXT_PUBLIC_API_URL=http://localhost:5001/api
```

**Backend (`backend/.env`):**
```env
PORT=5001
LLM_API_KEY=your_api_key_here
```

### 1. Backend Setup

1. Open a terminal and navigate to the `backend` directory:
   ```bash
   cd backend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the development server (runs on `http://localhost:5001`):
   ```bash
   npm run dev
   ```

### 2. Frontend Setup

1. Open another terminal and navigate to the `frontend` directory:
   ```bash
   cd frontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the Next.js development server (runs on `http://localhost:3000`):
   ```bash
   npm run dev
   ```

## API Documentation

The backend provides the following endpoints:

### `POST /api/chat`
Handles AI Chat Assistant messages.

**Request Body:**
```json
{
  "message": "How do I register to vote?"
}
```

**Response:**
```json
{
  "reply": "Voter registration is the first step! You need to be a citizen and at least 18 years old..."
}
```

## Scalability & AI Integration

- **AI Integration**: The chatbot is modularized in `backend/src/routes/chat.ts`. Currently, it uses a fast pattern-matching system for the mock dataset, but is designed to drop-in replace the `getMockAIResponse` function with an LLM SDK (like OpenAI's or Gemini's) with a structured prompt.
- **Scalability**: By separating the frontend (Next.js) and backend (Express), we ensure the UI can scale independently of the AI processing server. Using TypeScript across both layers provides type-safety and easier maintenance.

## Design

The UI is built strictly according to a portfolio-quality standard using Stitch concepts:
- **Visual Hierarchy**: Clear distinction between primary actions (Start Learning) and secondary information.
- **Micro-animations**: Provided via Framer Motion to give immediate feedback when interacting with timelines and quizzes.
- **Trustworthy Palette**: A base of slate/white with varying shades of blue (primary action color) to evoke trust and clarity suitable for civic education.
