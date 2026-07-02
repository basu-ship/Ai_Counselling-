AI Student Counselling
AI Student Counselling is a full-stack web app that helps students reflect on their mood, analyze stress signals from written text, and view sample journal entries. The project combines a React frontend with a FastAPI backend that exposes a simple mood analysis API.
Note: This app is a student support and learning project. It is not a substitute for professional mental health care, counselling, or medical advice.

Features
Home page introducing the counselling assistant
Mood logging page with text input
Stress level analysis through a backend API
Polarity, subjectivity, and suggestion response fields
Color-coded results for low, medium, and high stress levels
Journal page with example entries
Responsive navigation bar and clean card-based UI
Separate frontend and backend folders for full-stack development
Tech Stack
Frontend
React 19
Vite 7
React Router DOM
CSS modules/files for page and component styling
Backend
Python
FastAPI
Uvicorn
Pydantic
TextBlob
CORS middleware for frontend/backend communication
Project Structure
ai-student-counselling/
+-- backend/
|   +-- main.py
|   +-- requirements.txt
|   +-- stress_detector.py
+-- frontend/
|   +-- public/
|   +-- src/
|   |   +-- components/
|   |   |   +-- Navbar.css
|   |   |   +-- Navbar.jsx
|   |   +-- pages/
|   |   |   +-- Home.jsx
|   |   |   +-- Journal.jsx
|   |   |   +-- LogMood.css
|   |   |   +-- LogMood.jsx
|   |   +-- App.css
|   |   +-- App.jsx
|   |   +-- index.css
|   |   +-- main.jsx
|   +-- package.json
|   +-- vite.config.js
+-- README.md
Getting Started
Prerequisites
Make sure these are installed:
Python 3.10 or newer
Node.js and npm
Backend Setup
From the project root:
cd backend
python -m venv .venv
Activate the virtual environment.
On Windows PowerShell:
.venv\Scripts\Activate.ps1
On macOS/Linux:
source .venv/bin/activate
Install backend dependencies:
pip install -r requirements.txt
Run the FastAPI server:
uvicorn main:app --reload
The backend will run at:
http://127.0.0.1:8000
Frontend Setup
Open a second terminal from the project root:
cd frontend
npm install
npm run dev
The frontend will run at:
http://localhost:5173
Keep both the backend and frontend servers running while using the app.
Available Frontend Scripts
npm run dev
Starts the Vite development server.
npm run build
Creates a production build.
npm run preview
Previews the production build locally.
npm run lint
Runs ESLint checks.
API Endpoints
Health Check
GET /
Example response:
{
  "status": "Backend is running"
}
Analyze Mood
POST /analyze
Request body:
{
  "text": "I feel stressed about my exams."
}
Example response:
{
  "stress_level": "High",
  "polarity": 0.5,
  "subjectivity": 0.6,
  "suggestion": "Take a short break and relax."
}
Main Routes
/ - Home page
/logmood - Mood input and stress analysis page
/journal - Journal entries page
How It Works
The user writes about their mood on the Log Mood page.
The frontend sends the text to http://127.0.0.1:8000/analyze.
The FastAPI backend analyzes the text and returns stress data.
The frontend displays the stress level, sentiment values, and a suggestion.
The current API in backend/main.py uses simple keyword-based demo logic. The backend/stress_detector.py file includes a TextBlob-based helper that can be connected to the API for sentiment-driven stress detection.
Future Improvements
Connect stress_detector.py directly to the /analyze endpoint
Store journal entries in a database
Add user authentication
Add mood history and trend charts
Add emergency support resources
Improve stress analysis with a trained machine learning model
Add tests for backend API and frontend interactions
Author
Basudev Mondal
GitHub: basu-ship
