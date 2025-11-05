# Carrer-Based-Ai-Recommendation-System

<p align="center">
  <img src="ChatGPT Image Nov 5, 2025, 02_43_09 PM.png" alt="AI Career Recommendation System Banner" width="100%">
</p>

An AI-powered Career Recommendation System that analyzes your skills, education, interests, or resume (PDF) and recommends the most suitable career paths using Machine Learning and Natural Language Processing.

Built with - FastAPI (backend), Streamlit (frontend), Sentence Transformers and NLP, SQLite(Database), it provides intelligent, explainable, and interactive career guidance.

## 🚀 Features
### 🧠 AI-Powered Career Matching

Uses SentenceTransformer (all-MiniLM-L6-v2) for semantic similarity between your skills and career data.

Understands meaning, not just keywords — “Machine Learning” ≈ “ML Engineer”.

### 📄 Resume Upload & Parsing

Upload your PDF resume and it automatically extracts:

Skills

Education

Interests

Powered by PyMuPDF for PDF text extraction and spaCy for NLP parsing.

### 💬 Explainability Layer

Shows which skills matched for each recommended career.

Example:

✅ Matched Skills: python, machine learning, statistics

### 💾 Database Integration

Stores user inputs and recommendations using SQLite.

Comes preloaded with a dataset of 25+ real-world careers across tech, data, design, business, and marketing domains.

### 💰 Enhanced Career Dataset

Each career includes:

career_name

description

required_skills

domain

average_salary

education_path

### ⚡ Full Stack Architecture

Frontend: Streamlit

Backend: FastAPI

Database: SQLite

ML/NLP: Sentence Transformers + spaCy

### Project Structure

career-recommendation-system/
│
├── backend/
│   ├── main.py                # FastAPI entry point
│   ├── model.py               # ML model & semantic recommender
│   ├── resume_parser.py       # PDF resume parsing using spaCy + PyMuPDF
│   ├── database.py            # SQLite connection & setup
│   ├── schemas.py             # Pydantic schemas for API validation
│   ├── seed_data.py           # Loads dataset into database
│   ├── careers_seed.csv       # Enhanced dataset (25+ careers)
│
├── frontend/
│   ├── app.py                 # Streamlit frontend
│   ├── utils.py               # Helper functions
│
├── database/
│   └── careers.db             # Auto-generated SQLite database
│
├── run_all.bat                # One-click start for both frontend + backend
├── README.md
└── banner.png                 # GitHub project banner

## ⚙️ Installation & Setup
### 1️⃣ Clone this repository
git clone https://github.com/testgithubrittttttt/career-recommendation-system.git
cd career-recommendation-system

### 2️⃣ Create & activate virtual environment
python -m venv .venv
.venv\Scripts\activate

### 3️⃣ Install dependencies
pip install -r requirements.txt
python -m spacy download en_core_web_sm

### 4️⃣ Seed the database with the dataset
cd backend
python seed_data.py


You should see:

✅ Successfully seeded 25 careers into the database!

### 5️⃣ Run the backend
uvicorn main:app --reload --host 127.0.0.1 --port 8000


Backend will run on → http://127.0.0.1:8000

### 6️⃣ Run the frontend
cd ../frontend
streamlit run app.py


Frontend will open in browser → http://localhost:8501

✅ Now you can upload a resume or enter skills manually to get recommendations!

## 🧾 Example Flow
### 🧍‍♂️ User Input:

Education: B.Tech in Computer Science

Skills: Python, Machine Learning, SQL, Statistics

Interests: AI, Data Analysis

### ⚙️ Backend Processing:

Converts user text → Embeddings using SentenceTransformer

Computes cosine similarity with career embeddings

Retrieves top 3 matches with matched skill explanation

### 🧠 Output Example:
Rank	Career	Match Score	Matched Skills
1	Data Scientist	0.84	python, machine learning, statistics
2	Machine Learning Engineer	0.80	python, machine learning
3	Data Analyst	0.77	python, sql

## 📚 Dataset Overview
Field	Description
career_name	Job title
description	Role summary
required_skills	Skills needed
domain	Domain / industry
average_salary	Average annual salary
education_path	Common education background
Example Entries:
Career	Domain	Avg Salary	Skills
Data Scientist	Data Science	120000	python, ml, statistics, sql
UI/UX Designer	Design	70000	figma, design thinking, adobe xd
DevOps Engineer	Cloud	110000	docker, aws, kubernetes, ci/cd

## 🧰 Tech Stack
Layer	Tools / Frameworks
Frontend	Streamlit
Backend	FastAPI
Database	SQLite
NLP & ML	SentenceTransformer, spaCy, PyMuPDF
Language	Python 3.11
Deployment	Uvicorn, Streamlit CLI

## 🧩 Advanced Features

📄 Resume Parsing API → /parse_resume

🔍 Career Recommendation API → /predict

🧠 Skill Overlap Explainability

💾 Database Logging for users & recommendations

🌐 CORS Enabled for full-stack communication

📊 Future Enhancements

🌍 Add job market APIs (LinkedIn / Indeed)

📈 Salary and domain visualization dashboard (bar & pie charts)

🗂️ Admin panel for managing career data

🤖 Deploy on Render / Hugging Face Spaces

## 💼 Author

Dhruv Sharma
🎓 AI / ML Developer & Data Science Enthusiast
📧 [Your Email or Portfolio Link]
🔗 LinkedIn Profile

## 🌟 Star this repo if you found it helpful!

## 📜 License

This project is open-source under the MIT License — free to use and modify with credit.
