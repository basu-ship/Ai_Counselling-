# AI Student Counselling

AI Student Counselling is a full-stack web app that helps students write about their mood and get a simple stress analysis. It uses a React frontend and a FastAPI backend.

> Note: This project is for student support and learning. It is not a replacement for professional mental health care.

## Features

- Mood logging with text input
- Stress level analysis through a backend API
- Polarity, subjectivity, and suggestion results
- Color-coded low, medium, and high stress responses
- Journal page with sample entries
- Responsive navigation and clean UI

## Tech Stack

- Frontend: React, Vite, React Router DOM, CSS
- Backend: Python, FastAPI, Uvicorn, Pydantic, TextBlob

## Project Structure

```text
ai-student-counselling/
+-- backend/
|   +-- main.py
|   +-- requirements.txt
|   +-- stress_detector.py
+-- frontend/
|   +-- src/
|   |   +-- components/
|   |   +-- pages/
|   |   +-- App.jsx
|   |   +-- main.jsx
|   +-- package.json
+-- README.md
```

## Setup

### Backend

```bash
cd backend
python -m venv .venv
pip install -r requirements.txt
uvicorn main:app --reload
```

Backend URL:

```text
http://127.0.0.1:8000
```

### Frontend

Open another terminal:

```bash
cd frontend
npm install
npm run dev
```

Frontend URL:

```text
http://localhost:5173
```

## API

- `GET /` - Checks if the backend is running
- `POST /analyze` - Accepts mood text and returns stress level, polarity, subjectivity, and a suggestion

Example request:

```json
{
  "text": "I feel stressed about my exams."
}
```

## Routes

- `/` - Home page
- `/logmood` - Mood analysis page
- `/journal` - Journal entries page

## Future Improvements

- Connect `stress_detector.py` directly to the API
- Store journal entries in a database
- Add user login and mood history
- Improve analysis with a machine learning model

## Author

Basudev Mondal

- GitHub: [basu-ship](https://github.com/basu-ship)
