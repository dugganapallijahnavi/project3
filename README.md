The Full-Stack Resume Analyzer is a web application designed to help job seekers improve their resumes. Users can upload their resumes in PDF format, and the application, powered by the Google Gemini LLM, will automatically analyze the content, extract key information, and provide insightful feedback for improvement. The application also includes a historical viewer to track past analyses.

✨ Features
Live Analysis: Instantly analyze a PDF resume to get structured data and AI-driven feedback.

AI-Powered Insights: Receive a resume rating, a summary of improvement areas, and a list of suggested skills to learn.

Data Extraction: The application extracts key details like personal information, work experience, education, and skills.

Historical Viewer: View a table of all previously analyzed resumes.

Detailed View: Click on any historical entry to see the full, detailed analysis in a modal.

Database Storage: All analyzed data is securely stored in a PostgreSQL database for future reference.

💻 Technology Stack
Frontend: React.js

Backend: Node.js, Express.js

Database: PostgreSQL

LLM Integration: Google Gemini API via @google/generative-ai SDK

PDF Parsing: pdf-parse

File Handling: multer

Styling: Plain CSS or a utility-first framework like Tailwind CSS (recommended for ease of use)

📂 Project Structure
The repository is organized into two main directories: frontend and backend.

/resume-analyzer
├── backend/                  # Node.js backend
│   ├── controllers/          # Business logic for API endpoints
│   ├── routes/               # API route definitions
│   ├── services/             # Core logic for PDF and LLM interaction
│   ├── .env.example          # Example environment variables file
│   └── server.js             # Main server file
├── frontend/                 # React frontend
│   ├── public/
│   ├── src/                  # React components and logic
│   └── package.json
├── sample_data/              # Sample resumes for testing
├── screenshots/              # Screenshots of the application UI
└── README.md                 # This file
⚙️ Setup and Installation
Follow these steps to get the project up and running on your local machine.

Step 1: Clone the repository
Bash

git clone https://github.com/your-username/resume-analyzer.git
cd resume-analyzer
Step 2: Set up the PostgreSQL database
Ensure you have PostgreSQL installed and running. Create a new database for this project.

Create the resumes table:

SQL

CREATE TABLE resumes (
    id SERIAL PRIMARY KEY,
    file_name VARCHAR(255) NOT NULL,
    uploaded_at TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP,
    name VARCHAR(255),
    email VARCHAR(255),
    analysis JSONB NOT NULL
);
Note: You can add more columns to the table to store key pieces of data directly for easier querying (e.g., resume_rating, technical_skills), but storing the full JSON analysis in a JSONB column is essential.

Step 3: Backend Setup
Navigate to the backend directory, install dependencies, and configure your environment variables.

Bash

cd backend
npm install
Create a .env file based on the .env.example template and fill in your details:

PORT=5000
DB_USER=your_postgres_user
DB_HOST=localhost
DB_DATABASE=your_db_name
DB_PASSWORD=your_postgres_password
DB_PORT=5432
GOOGLE_API_KEY="YOUR_GEMINI_API_KEY"
You can obtain a Google Gemini API key from the Google AI for Developers website.

Run the backend server:

Bash

npm start
The backend should now be running on http://localhost:5000.

Step 4: Frontend Setup
Open a new terminal, navigate to the frontend directory, and install dependencies.

Bash

cd ../frontend
npm install
Run the React development server:

Bash

npm start
The frontend should now be available at http://localhost:3000.

📷 Screenshots
Here are some screenshots of the application in action.

Live Analysis Tab: The main page with the file upload form.

Analysis Results: The results of a resume analysis showing structured data and AI feedback.

Historical Viewer Tab: A table displaying a list of all past analyses.

Details Modal: A modal showing the full analysis for a historical resume.

📝 Evaluation Criteria
The project will be evaluated based on the following criteria:

Functionality: All features (upload, analysis, history, details modal) work as described.

Code Quality: Clean, well-structured, and readable code following best practices.

Data Accuracy: The accuracy and completeness of the data extracted by the LLM.

AI Insights: The relevance and quality of the AI-generated feedback and suggestions.

UI/UX: An intuitive, visually appealing, and responsive user interface.
