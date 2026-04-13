# PROBLEM STATEMENT : Disaster preparedness and Response Education System For Schools and Colleges


# 🚨 Disaster Awareness Portal (DAP)

A full-stack MERN-based educational platform designed to teach students disaster preparedness through interactive modules, quizzes, and AI-powered assistance.

## 🌟 Features

* 📚 Interactive Disaster Modules (Before, During, After, Do’s & Don’ts)
* 🎥 Video-based Learning with Transcripts
* 🧠 AI Chatbot (Local LLM using Ollama)
* 📝 Quiz System with Levels (Very Easy → Hard)
* 📊 Progress Tracking & Leaderboard
* 🏫 Role-based Access (Admin, Principal, Student)
* 🎫 Support Ticket System (Student & School Issues)
* 🧑‍💼 Admin Dashboard with Analytics
* 🔐 Authentication & Authorization (JWT)

## 🏗️ Tech Stack

### Frontend

* React.js (Vite)
* React Router DOM
* Axios / Fetch API
* Custom CSS (Glassmorphism UI)

### Backend

* Node.js
* Express.js
* MongoDB
* Mongoose

### AI Integration

* Ollama (Local LLM)
* LLaMA 3 / Phi-3 / Mistral

## 📁 Project Structure

```
/client        → React Frontend
/server        → Express Backend
/uploads       → Stored Videos & Images
```

---

## 🚀 Installation & Setup

### 1️⃣ Clone Repository

```
git clone https://github.com/your-username/disaster-awareness-portal.git
cd disaster-awareness-portal
```

---

### 2️⃣ Backend Setup

```
cd server
npm install
```

Create `.env` file:

```
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key
PORT=5000
```

---

### 📁 Create Upload Folder (IMPORTANT)

```
server/uploads/modules
```

---

### ▶️ Run Backend

```
npm run dev
```

Backend runs on:

```
http://localhost:5000
```

---

### 3️⃣ Frontend Setup

Open new terminal:

```
cd client
npm install
npm run dev
```

Frontend runs on:

```
http://localhost:5173
```

---

## 🤖 AI Chatbot Setup (LOCAL - NO API LIMITS)

Install Ollama:
👉 https://ollama.com/download

Pull model:

```
ollama pull phi3
```

Run model:

```
ollama run phi3
```

API Endpoint:

```
http://localhost:11434/api/generate
```

---

## 🧠 AI Architecture

```
User Question
      ↓
Frontend (React)
      ↓
Backend (Express)
      ↓
Ollama Local API
      ↓
LLM (LLaMA 3 / Phi-3)
      ↓
Response to UI
```

---

## 🔐 Authentication & Security

Passwords are securely hashed using **bcrypt**:

* Prevents storing plain text passwords
* Ensures secure authentication
* npm install bcryptjs

### Example:

```
const hashedPassword = await bcrypt.hash(password, 10);
const isMatch = await bcrypt.compare(password, user.password);
```

---

## 📊 PDF Reports & Analytics

The system uses **PDFKit** to generate downloadable reports:

* Student progress reports
* Quiz performance
* Graph-based analytics
* npm install jspdf
* If you want to export charts or UI:

Install extra package:

npm install html2canvas

### Example:

```
const doc = new PDFDocument();
doc.text("Student Progress Report");
doc.end();
```

### Graph Integration:
Recharts does NOT need extra dependencies
Error: "Cannot find module 'recharts'"
✔ Fix:
npm install recharts



## 🎓 Quiz Levels

| Level     | Class Range |
| --------- | ----------- |
| Very Easy | Below 3rd   |
| Easy      | 3rd - 5th   |
| Medium    | 6th - 8th   |
| Hard      | 9th - 10th  |

---

## 🎫 Ticket System

* Student Issue → Linked to studentId
* School Issue → Raised by principal
* Admin can:

  * View all tickets
  * Update status (Open / In Progress / Resolved)

---

## 🔐 Roles

* 👨‍💼 Admin
* 🧑‍🏫 Principal
* 🎓 Student

---

## 📦 Key Functionalities

* Dynamic Module Unlocking
* Video + Transcript Learning
* AI Chatbot Assistance
* Quiz Evaluation System
* Progress Tracking Dashboard
* Role-based Dashboards

---

## ⚠️ Common Issues & Fixes

### ❌ Images / Videos not loading

✔ Ensure backend static config:

```
app.use("/uploads", express.static("uploads"));
```

✔ Correct URL format:

```
http://localhost:5000/uploads/modules/filename.png
```

---

### ❌ AI not responding

✔ Ensure Ollama is running:

```
ollama run phi3
```

---

### ❌ Module not loading

✔ Check MongoDB connection in `.env`

---

## 🛑 Stop the Project

Press:

```
Ctrl + C
```

in both terminals

---

## 🚀 Deployment (Optional)

* Frontend → Vercel / Netlify
* Backend → Render / Railway
* Database → MongoDB Atlas




## ⭐ Support

If you like this project, give it a ⭐ on GitHub!
