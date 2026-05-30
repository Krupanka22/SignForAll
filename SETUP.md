# 🚀 Complete Setup Guide - Sign Language Translator

A step-by-step guide to get the Sign Language Translator running on your machine.

---

## Prerequisites Checklist

Before starting, ensure you have:

- [ ] **Python 3.10+** - [Download](https://www.python.org/downloads/)
- [ ] **Node.js 16+** - [Download](https://nodejs.org/)
- [ ] **Git** - [Download](https://git-scm.com/)
- [ ] **~5GB free disk space** (for dependencies & models)
- [ ] **4GB RAM minimum** (8GB recommended)

### Verify Installation

```bash
# Check Python version
python --version
# Expected: Python 3.10.x or higher

# Check Node.js version
node --version
# Expected: v16.x.x or higher

# Check npm version
npm --version
# Expected: 8.x.x or higher
```

---

## 📥 Step 1: Clone the Repository

```bash
git clone https://github.com/your-username/sign-language-translator.git
cd sign-language-translator
```

---

## 🔧 Step 2: Backend Setup

### 2.1 Navigate to Backend Directory

```bash
cd sign_language_translator-backend
```

### 2.2 Create Virtual Environment

A virtual environment isolates Python packages for this project.

```bash
# Create virtual environment
python -m venv venv
```

**⏱️ Time:** ~30 seconds

### 2.3 Activate Virtual Environment

**Windows (PowerShell):**
```powershell
.\venv\Scripts\Activate.ps1
```

**Windows (Command Prompt):**
```cmd
venv\Scripts\activate
```

**Mac/Linux:**
```bash
source venv/bin/activate
```

✅ You should see `(venv)` prefix in your terminal

### 2.4 Upgrade pip

```bash
pip install --upgrade pip
```

⏱️ Time:** ~1 minute

### 2.5 Install Python Dependencies

```bash
pip install -r requirements.txt
```

**⏱️ Time:** 5-15 minutes (depends on internet speed)

### 2.6 Download spaCy English Model

Required for natural language processing:

```bash
python -m spacy download en_core_web_sm
```

**⏱️ Time:** ~2 minutes  
**Size:** ~40MB

### 2.7 Verify Installation

```bash
pip list
```

Should show all packages including:
- Flask
- TensorFlow
- Spacy
- OpenCV
- MediaPipe

---

## 🎨 Step 3: Frontend Setup

### 3.1 Navigate to Frontend Directory

```bash
# Go back to root first (if you're in backend)
cd ..

# Then navigate to frontend
cd sign_language_translator-frontend
```

### 3.2 Install Dependencies

```bash
npm install
```

**⏱️ Time:** 3-5 minutes  
**Size:** ~500MB (node_modules folder)

### 3.3 Verify Installation

```bash
npm list --depth=0
```

Should show React, Vite, Tailwind CSS, and other packages

---

## ▶️ Step 4: Run the Application

### 4.1 Start Backend Server

**Open Terminal 1:**

```bash
cd sign_language_translator-backend

# Activate venv (if not already activated)
.\venv\Scripts\Activate.ps1  # Windows PowerShell
# or
source venv/bin/activate     # Mac/Linux

# Start Flask app
python app.py
```

**Expected Output:**
```
 * Running on all addresses (0.0.0.0)
 * Running on http://127.0.0.1:5000
```

✅ Backend is ready!

### 4.2 Start Frontend Development Server

**Open Terminal 2 (new window):**

```bash
cd sign_language_translator-frontend
npm run dev
```

**Expected Output:**
```
  VITE v5.x.x  ready in xxx ms

  ➜  Local:   http://localhost:5173/
```

✅ Frontend is ready!

### 4.3 Access the Application

- **Open Browser:** `http://localhost:5173`
- **Backend API:** `http://localhost:5000`

🎉 **Application is now running!**

---

## 📦 Project Structure

```
sign-language-translator/
├── sign_language_translator-backend/
│   ├── venv/                      # Virtual environment (ignore in git)
│   ├── app.py                     # Main Flask application
│   ├── requirements.txt           # Python dependencies
│   ├── isl_nlp_pipeline/          # NLP processing
│   └── ISL_text/                  # Sign recognition model
│
├── sign_language_translator-frontend/
│   ├── node_modules/              # Dependencies (ignore in git)
│   ├── src/                       # React components
│   ├── package.json               # Node dependencies
│   └── vite.config.js             # Vite configuration
│
├── README.md                      # Main documentation
├── SETUP.md                       # This file
└── .gitignore                     # Git ignore rules
```

---

## 🔄 Daily Workflow

### To Start Development (Every Day)

**Terminal 1 - Backend:**
```bash
cd sign_language_translator-backend
.\venv\Scripts\Activate.ps1  # or source venv/bin/activate
python app.py
```

**Terminal 2 - Frontend:**
```bash
cd sign_language_translator-frontend
npm run dev
```

### To Stop the Application

- **Backend:** Press `Ctrl+C` in Terminal 1
- **Frontend:** Press `Ctrl+C` in Terminal 2

### To Deactivate Virtual Environment

```bash
deactivate
```

---

## 📋 Useful Commands

### Backend Commands

```bash
# Show installed packages
pip list

# Update all packages
pip install --upgrade pip

# Generate requirements from environment
pip freeze > requirements.txt

# Run tests
python test_pipeline.py
```

### Frontend Commands

```bash
# Build for production
npm run build

# Preview production build
npm run preview

# Run linter
npm run lint

# Format code
npm run format
```

---

## 🚨 Common Issues & Solutions

### Issue: "ModuleNotFoundError: No module named 'flask'"

**Cause:** Virtual environment not activated

**Solution:**
```bash
.\venv\Scripts\Activate.ps1  # Windows PowerShell
# or
source venv/bin/activate     # Mac/Linux
```

---

### Issue: "OSError: Can't find model 'en_core_web_sm'"

**Cause:** spaCy model not downloaded

**Solution:**
```bash
python -m spacy download en_core_web_sm
```

---

### Issue: "Address already in use" (port 5000 or 5173)

**Cause:** Another process using the port

**Solution (Windows):**
```bash
# Find process using port 5000
netstat -ano | findstr :5000

# Kill the process (replace PID)
taskkill /PID <PID> /F
```

**Solution (Mac/Linux):**
```bash
# Kill process using port 5000
lsof -ti:5000 | xargs kill -9
```

---

### Issue: "npm: command not found"

**Cause:** Node.js/npm not installed or not in PATH

**Solution:**
- Download from [nodejs.org](https://nodejs.org/)
- Restart terminal after installation
- Verify: `node --version`

---

## 📚 Next Steps

1. **Explore the API:**
   - Visit `http://localhost:5000`
   - Test endpoints using Postman or curl

2. **Try the Features:**
   - Text to ISL translation
   - ISL to Text recognition
   - Upload images/videos

3. **Read the Code:**
   - Backend: `sign_language_translator-backend/app.py`
   - Frontend: `sign_language_translator-frontend/src/App.jsx`

4. **Make Changes:**
   - Backend changes: Restart Flask server
   - Frontend changes: Auto-reload with Vite

---

## 🤝 Contributing

1. Create a feature branch: `git checkout -b feature/your-feature`
2. Make your changes
3. Commit: `git commit -m 'Add your feature'`
4. Push: `git push origin feature/your-feature`
5. Create a Pull Request

---

## 📞 Support

For issues or questions:
- Check [Troubleshooting](#-common-issues--solutions) section
- Open a GitHub issue
- Check existing issues for similar problems

---

## ✅ Setup Checklist

- [ ] Python 3.10+ installed
- [ ] Node.js 16+ installed
- [ ] Repository cloned
- [ ] Virtual environment created
- [ ] Backend dependencies installed
- [ ] spaCy model downloaded
- [ ] Frontend dependencies installed
- [ ] Backend server running on port 5000
- [ ] Frontend server running on port 5173
- [ ] Application accessible at `http://localhost:5173`

---

**🎉 You're all set! Happy coding!**
