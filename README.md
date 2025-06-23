# Crossword Blitz

## Overview

Crossword Blitz is a competitive, real-time multiplayer crossword puzzle game designed for up to four players. Based on the concept outlined in `Project.md`, the goal is to provide a fun, timed, head-to-head environment where players solve the same puzzle on independent grids, aiming for the fastest completion time while minimizing penalties from incorrect letters.

This repository contains the source code for both the frontend and backend components.

## Project Structure

```
CrosswordBlitz/
├── backend/           # FastAPI backend service
│   ├── src/             # Main Python source code (routers, models, utils)
│   ├── resources/       # Puzzle files (.puz)
│   ├── requirements.txt # Python dependencies
│   └── ...              # Dockerfile, etc.
├── frontend/          # React frontend application
│   ├── src/             # Main TypeScript/React source code (components, types, etc.)
│   ├── public/          # Static assets
│   ├── package.json     # Node dependencies
│   └── ...              # Vite config, TS config, Dockerfile, etc.
├── docker-compose.yml # Docker orchestration for development
├── Project.md         # Detailed product design document
└── README.md          # This file
```

*   **Backend:** Built with Python and FastAPI, responsible for serving puzzle data, managing game state (intended), and handling API requests.
*   **Frontend:** Built with React, TypeScript, and Vite, styled with Tailwind CSS (v3). Responsible for rendering the game interface, user interactions, and communicating with the backend.

## Prerequisites

*   [Node.js](https://nodejs.org/) (v18 or later recommended) and npm
*   [Python](https://www.python.org/) (v3.8 or later recommended) and pip
*   [Git](https://git-scm.com/)
*   [Docker](https://www.docker.com/products/docker-desktop/) and Docker Compose (Optional, for containerized setup)

## Getting Started (Local Development)

1.  **Clone the repository:**
    ```bash
    git clone <your-repository-url>
    cd CrosswordBlitz
    ```

2.  **Setup Backend:**
    ```bash
    cd backend

    # Create and activate a virtual environment (recommended)
    python -m venv venv
    source venv/bin/activate # On Windows use `venv\Scripts\activate`

    # Install dependencies
    pip install -r requirements.txt

    # Run the FastAPI development server (usually on http://localhost:8000)
    uvicorn src.main:app --reload --port 8000 
    # Note: Ensure src/main.py contains the FastAPI app instance named 'app'
    
    cd .. # Return to root directory
    ```
    *Note: Backend might require environment variables (e.g., for database or Supabase connection) defined in a `.env` file based on `.env.example` if applicable.* 

3.  **Setup Frontend:**
    ```bash
    cd frontend

    # Install dependencies
    npm install

    # Run the Vite development server (usually on http://localhost:5173)
    npm run dev

    cd .. # Return to root directory
    ```

4.  **Access the application:** Open your browser and navigate to `http://localhost:5173` (or the port specified by Vite).

## Running with Docker (Optional)

If you have Docker and Docker Compose installed, you can build and run the services using:

```bash
docker compose up --build
```

This command will build the images defined in the `Dockerfile`s for both frontend and backend and start the containers as specified in `docker-compose.yml`. The frontend should be accessible at `http://localhost:5173` and the backend at `http://localhost:8000` (verify ports in `docker-compose.yml`). 
