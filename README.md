# InterviewEdge 🎯

A Gen AI job preparation platform. Upload your resume and a job description, see where your skills fall short, practise with role-specific interview questions, and download an ATS-friendly version of your resume.

**Live demo:** https://interviewedge-frontend-xlwh.onrender.com/

<!-- Add 2-3 screenshots here -->
<img width="1356" height="681" alt="image" src="https://github.com/user-attachments/assets/f415ce74-bf3a-43ed-b849-a602479df649" />

## Features

- **Resume + job description analysis:** upload both and get a skill-gap analysis showing what matches and what's missing
- **AI-generated interview questions:** role-specific questions created with the Gemini API, based on your resume and the job
- **Skill extraction:** pulls skills out of your resume automatically
- **ATS-friendly resume PDF:** generates a downloadable, ATS-friendly version of your resume using Puppeteer
- **Secure authentication:** JWT login, with token blacklisting so a session really ends when you log out

## Tech Stack

| Area | Technologies |
|------|--------------|
| Frontend | React.js |
| Backend | Node.js, Express.js |
| AI | Gemini API (via REST APIs) |
| Auth | JWT with token blacklisting |
| PDF generation | Puppeteer |
| Deployment | Render |

## How It Works

1. The user logs in and uploads a resume and a job description.
2. The backend sends them to the Gemini API, which extracts the resume's skills and compares them with the job's requirements.
3. The app shows the skill gaps and generates interview questions for that role.
4. The user can download an ATS-friendly resume as a PDF.

## Authentication Note

JWTs are stateless, so a token would stay valid after logout until it expired. InterviewEdge saves logged-out tokens in a blacklist and checks it on every protected request, so a token stops working as soon as the user logs out.

## Getting Started

```bash
git clone https://github.com/aditi-sharma7/InterviewEdge.git
cd InterviewEdge
```

Install and run the backend:

```bash
cd backend
npm install
npm start
```

Install and run the frontend:

```bash
cd frontend
npm install
npm run dev
```

Create a `.env` file in the backend folder:

```
PORT=3000
MONGO_URI=your_database_connection_string
JWT_SECRET=your_jwt_secret
GEMINI_API_KEY=your_gemini_api_key
```

## Author

**Aditi Sharma**: [LinkedIn](https://linkedin.com/in/aditisharma63) · [GitHub](https://github.com/aditi-sharma7)
