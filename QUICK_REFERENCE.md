# ⚡ Quick Reference

## 🚀 Quick Start (Copy-Paste)

### Windows PowerShell

```powershell
# Clone
git clone https://github.com/your-username/sign-language-translator.git
cd sign-language-translator

# Backend Setup
cd sign_language_translator-backend
python -m venv venv
.\venv\Scripts\Activate.ps1
pip install --upgrade pip
pip install -r requirements.txt
python -m spacy download en_core_web_sm

# Run Backend (keep this terminal open)
python app.py

# In new terminal - Frontend Setup
cd sign_language_translator-frontend
npm install
npm run dev
```

### Mac/Linux

```bash
# Clone
git clone https://github.com/your-username/sign-language-translator.git
cd sign-language-translator

# Backend Setup
cd sign_language_translator-backend
python -m venv venv
source venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
python -m spacy download en_core_web_sm

# Run Backend (keep this terminal open)
python app.py

# In new terminal - Frontend Setup
cd sign_language_translator-frontend
npm install
npm run dev
```

---

## 📍 Access Points

| Service | URL | Purpose |
|---------|-----|---------|
| Frontend | `http://localhost:5173` | Web application |
| Backend API | `http://localhost:5000` | REST API |

---

## 🔑 Key Commands

### Backend
```bash
cd sign_language_translator-backend
.\venv\Scripts\Activate.ps1           # Activate venv
pip install -r requirements.txt       # Install packages
python -m spacy download en_core_web_sm  # Download NLP model
python app.py                         # Start server
deactivate                            # Deactivate venv
```

### Frontend
```bash
cd sign_language_translator-frontend
npm install                           # Install packages
npm run dev                           # Start dev server
npm run build                         # Build for production
npm run preview                       # Preview build
```

---

## 📦 Dependencies Summary

### Backend (requirements.txt)
- **Web:** Flask 3.1.0, flask-cors 5.0.1
- **ML:** TensorFlow 2.19.0, Keras 3.12.2+
- **Vision:** OpenCV 4.11.0.86, MediaPipe 0.10.21
- **NLP:** spaCy 3.8.4, TextBlob 0.17.1
- **Utils:** NumPy 1.26.4, scikit-learn 1.6.1, requests 2.32.3

### Frontend (package.json)
- React 18+
- Vite (build tool)
- Tailwind CSS
- JavaScript ES6+

---

## 🐛 Quick Fixes

| Problem | Solution |
|---------|----------|
| `ModuleNotFoundError: flask` | Activate venv: `.\venv\Scripts\Activate.ps1` |
| `Can't find model 'en_core_web_sm'` | `python -m spacy download en_core_web_sm` |
| Port 5000/5173 in use | `netstat -ano \| findstr :5000` then kill process |
| `npm: command not found` | Install Node.js from nodejs.org |
| `node_modules` errors | Delete folder: `rm -r node_modules` then `npm install` |

---

## 📂 Project Structure

```
sign-language-translator/
├── sign_language_translator-backend/
│   ├── venv/                    # Virtual env (ignore)
│   ├── app.py                   # Main Flask app
│   ├── requirements.txt         # Python dependencies
│   ├── isl_nlp_pipeline/        # NLP module
│   └── ISL_text/                # Sign recognition
│
├── sign_language_translator-frontend/
│   ├── node_modules/            # Dependencies (ignore)
│   ├── src/                     # React components
│   ├── public/                  # Static files
│   └── package.json             # Node dependencies
│
├── README.md                    # Full documentation
├── SETUP.md                     # Detailed setup guide
├── QUICK_REFERENCE.md           # This file
└── .gitignore                   # Git ignore rules
```

---

## 📝 Environment Files

### .gitignore (already configured)
- `venv/` - Python virtual environment
- `node_modules/` - Node dependencies
- `.env` - Environment variables
- `__pycache__/` - Python cache
- `dist/` - Build output

---

## 🔗 API Endpoints

```bash
# Health check
GET http://localhost:5000/

# Text to ISL
POST http://localhost:5000/api/text-to-gloss
Body: {"text": "Hello world"}

# ISL to Text
POST http://localhost:5000/api/gloss-to-text
Body: {"gloss": "HELLO WORLD"}

# Recognize sign
POST http://localhost:5000/api/recognize-sign
Body: {"image": "base64_encoded_image"}
```

---

## 💡 Pro Tips

1. **Keep terminals open** - Run backend and frontend simultaneously in different terminals
2. **Hot reload** - Frontend auto-reloads on code changes
3. **Backend changes** - Restart Flask server manually
4. **Clear cache** - Delete `node_modules` if you have issues
5. **Deactivate venv** - Type `deactivate` to exit virtual environment

---

## 📞 Need Help?

1. Check **README.md** - Full documentation
2. Check **SETUP.md** - Detailed setup guide
3. Check **Troubleshooting** section in README
4. Open GitHub issue with:
   - Error message
   - Your OS & versions
   - Steps to reproduce

---

**Happy coding! 🚀**
