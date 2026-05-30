# Sign Language Translator

> A comprehensive full-stack application that translates between **Indian Sign Language (ISL)** and **English text** in real-time.

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![React](https://img.shields.io/badge/React-18+-61dafb.svg)
![Flask](https://img.shields.io/badge/Flask-3.1.0-black.svg)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.19.0-orange.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

---

## Quick Start (5 Minutes)

### Prerequisites
- **Python 3.10+** ([Download](https://www.python.org/downloads/))
- **Node.js 16+** ([Download](https://nodejs.org/))
- **Git** ([Download](https://git-scm.com/))

### Clone & Setup
```bash
# Clone the repository
git clone https://github.com/your-username/sign-language-translator.git
cd sign-language-translator

# Backend Setup
cd sign_language_translator-backend
python -m venv venv
.\venv\Scripts\activate  # Windows
# source venv/bin/activate  # Mac/Linux

pip install -r requirements.txt
python -m spacy download en_core_web_sm
python app.py

# Frontend Setup (in new terminal)
cd sign_language_translator-frontend
npm install
npm run dev
```

**Backend running on:** `http://localhost:5000`  
**Frontend running on:** `http://localhost:5173`

---

## Features

| Feature | Description |
|---------|-------------|
| **Text to ISL** | Convert English text → Sign language videos |
| **ISL to Text** | Recognize signs from video/images → English text |
| **NLP Pipeline** | Advanced linguistic processing & transformation |
| **Real-time Processing** | Fast inference with optimized models |
| **Video Player** | Speed control, progress tracking, smooth playback |
| **Responsive UI** | Mobile-friendly interface with Tailwind CSS |

---

## Project Structure

```
sign_language_translator-backend/
├── app.py                          # Main Flask application
├── requirements.txt                # Python dependencies
├── isl_nlp_pipeline/              # NLP processing module
│   ├── app.py
│   ├── requirements.txt
│   ├── test_pipeline.py
│   ├── data/                      # Language data files
│   │   ├── time_words.txt
│   │   └── wh_words.txt
│   ├── gloss_to_text/             # Gloss to English conversion
│   │   ├── gloss_to_english.py
│   │   └── gloss_to_english_copy.py
│   ├── text_to_gloss/             # English to ISL gloss conversion
│   │   ├── main.py
│   │   ├── modules/               # NLP modules
│   │   │   ├── classifier.py
│   │   │   ├── extractor.py
│   │   │   ├── generator.py
│   │   │   ├── preprocessor.py
│   │   │   └── transformer.py
│   │   └── utils/
│   │       └── helpers.py
│   └── data/
├── ISL_text/                      # Sign language recognition module
│   ├── app.py
│   ├── predictor.py
│   ├── train_model.py
│   ├── isl_model.h5               # Trained deep learning model
│   ├── requirements.txt
│   ├── data/
│   │   ├── images/
│   │   └── videos/
│   ├── static/
│   │   └── index.html
│   └── uploads/
├── static/
│   └── index.html
└── uploads/

sign_language_translator-frontend/
├── src/
│   ├── App.jsx                    # Main app component
│   ├── Home.jsx                   # Home page
│   ├── About.jsx                  # About page
│   ├── main.jsx
│   ├── assets/                    # Static assets
│   ├── components/                # Reusable components
│   │   ├── Navbar.jsx
│   │   └── Footer.jsx
│   ├── isl-to-text/              # ISL to text page
│   │   └── ISL_To_Text.jsx
│   ├── text-to-isl/              # Text to ISL page
│   │   ├── Text_To_ISL.jsx
│   │   ├── components/           # Sub-components
│   │   │   ├── TextInput/
│   │   │   ├── VideoPlayer/
│   │   │   └── common/
│   │   ├── hooks/                # Custom React hooks
│   │   ├── utils/                # Utility functions
│   │   └── assets/
│   └── index.css
├── public/
│   ├── images/
│   └── sign-videos/
├── package.json
├── vite.config.js
├── tailwind.config.js
├── postcss.config.js
└── eslint.config.js
```

## Detailed Installation Guide

### Backend Setup

#### Step 1: Create Virtual Environment
```bash
cd sign_language_translator-backend
python -m venv venv
```

**Activate Virtual Environment:**
```bash
# Windows PowerShell
.\venv\Scripts\Activate.ps1

# Windows CMD
venv\Scripts\activate

# Mac/Linux
source venv/bin/activate
```

#### Step 2: Install Python Dependencies
```bash
# Upgrade pip
pip install --upgrade pip

# Install all requirements
pip install -r requirements.txt

# Download spaCy English model (required for NLP)
python -m spacy download en_core_web_sm
```

#### Step 3: Verify Installation
```bash
pip list  # Should show all packages
```

### Frontend Setup

#### Step 1: Install Node Dependencies
```bash
cd sign_language_translator-frontend
npm install
```

#### Step 2: Run Development Server
```bash
npm run dev
```

#### Step 3: Build for Production
```bash
npm run build
```

## Running the Application

### Start Backend Server
```bash
cd sign_language_translator-backend

# Activate virtual environment first
.\venv\Scripts\Activate.ps1  # Windows PowerShell
# or
source venv/bin/activate     # Mac/Linux

# Run the Flask app
python app.py
```

**Expected Output:**
```
 * Running on all addresses (0.0.0.0)
 * Running on http://127.0.0.1:5000
```

### Start Frontend Development Server
```bash
cd sign_language_translator-frontend
npm run dev
```

**Expected Output:**
```
  VITE v5.x.x  ready in xxx ms
  ➜  Local:   http://localhost:5173/
```

### Access the Application
- **Frontend:** Open browser → `http://localhost:5173`
- **Backend API:** `http://localhost:5000`
- **API Docs:** `http://localhost:5000/api/docs` (if Swagger configured)

## Dependencies

### Backend Dependencies (`sign_language_translator-backend/requirements.txt`)

#### Web Framework
| Package | Version | Purpose |
|---------|---------|---------|
| `Flask` | `3.1.0` | Python web framework |
| `flask-cors` | `5.0.1` | Enable CORS for API requests |

#### Machine Learning & Computer Vision
| Package | Version | Purpose |
|---------|---------|---------|
| `tensorflow` | `2.19.0` | Deep learning framework |
| `keras` | `3.12.2+` | Neural network API (auto-installed with TensorFlow) |
| `numpy` | `1.26.4` | Numerical computing |
| `scikit-learn` | `1.6.1` | Machine learning utilities |
| `opencv-python` | `4.11.0.86` | Computer vision library |
| `mediapipe` | `0.10.21` | Hand/pose detection |

#### Natural Language Processing
| Package | Version | Purpose |
|---------|---------|---------|
| `spacy` | `3.8.4` | NLP library (requires model download) |
| `textblob` | `0.17.1` | Text processing & analysis |
| `lemminflect` | `0.2.3` | Lemmatization & inflection |

#### Utilities
| Package | Version | Purpose |
|---------|---------|---------|
| `requests` | `2.32.3` | HTTP client |

**Total Size:** ~3GB (including TensorFlow & models)

### Frontend Dependencies

- **React** 18+
- **Vite** (build tool)
- **Tailwind CSS** (styling)
- **JavaScript ES6+**

See `sign_language_translator-frontend/package.json` for complete list.

### System Requirements
- **RAM:** 4GB minimum (8GB recommended)
- **Disk Space:** 5GB (3GB for Python packages + models)
- **GPU:** Optional (CPU will work, slower inference)

## API Endpoints

| Method | Endpoint | Purpose |
|--------|----------|---------|
| `GET` | `/` | Health check |
| `POST` | `/api/text-to-gloss` | Convert English text to ISL gloss |
| `POST` | `/api/gloss-to-text` | Convert ISL gloss to English text |
| `POST` | `/api/recognize-sign` | Recognize sign from image/video |
| `POST` | `/api/upload` | Upload image/video for processing |

### Request Examples

**Text to ISL Gloss**
```bash
curl -X POST http://localhost:5000/api/text-to-gloss \
  -H "Content-Type: application/json" \
  -d '{"text": "Hello world"}'
```

**ISL to Text**
```bash
curl -X POST http://localhost:5000/api/gloss-to-text \
  -H "Content-Type: application/json" \
  -d '{"gloss": "HELLO WORLD"}'
```

## Model Information

### ISL Recognition Model (`isl_model.h5`)
- Pre-trained deep learning model for ISL recognition
- Input: Image/Video frames
- Output: Predicted sign gestures with confidence scores
- Size: Optimized for real-time inference

## Development

### Code Style
- Follow PEP 8 for Python code
- Use ESLint rules for JavaScript/React code

### Testing

Run backend tests:
```bash
cd sign_language_translator-backend/isl_nlp_pipeline
python test_pipeline.py
```

Run frontend tests (if configured):
```bash
cd sign_language_translator-frontend
npm test
```

## Performance Optimization

- Video caching on frontend with `useVideoCache` hook
- Lazy loading of sign videos
- Optimized model inference
- Progressive image loading

## Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m 'Add your feature'`
4. Push to the branch: `git push origin feature/your-feature`
5. Submit a pull request

## Troubleshooting

### Backend Issues

**Error: "ModuleNotFoundError: No module named 'flask'"**
- Solution: Virtual environment not activated
  ```bash
  .\venv\Scripts\Activate.ps1  # Windows
  source venv/bin/activate     # Mac/Linux
  ```

**Error: "OSError: Can't find model 'en_core_web_sm'"**
- Solution: spaCy model not downloaded
  ```bash
  python -m spacy download en_core_web_sm
  ```

**Error: "Address already in use" (port 5000)**
- Solution: Kill existing process
  ```bash
  # Windows
  netstat -ano | findstr :5000
  taskkill /PID <PID> /F
  
  # Mac/Linux
  lsof -ti:5000 | xargs kill -9
  ```

**Error: TensorFlow GPU errors**
- Solution: Use CPU instead (add to app.py top)
  ```python
  import os
  os.environ['CUDA_VISIBLE_DEVICES'] = '-1'
  ```

### Frontend Issues

**Error: "Module not found" errors**
- Solution: Reinstall dependencies
  ```bash
  rm -r node_modules
  npm install
  npm run dev
  ```

**Error: Port 5173 already in use**
- Solution: Use different port
  ```bash
  npm run dev -- --port 3000
  ```

**Error: CORS errors when calling backend**
- Solution: Ensure backend is running
  ```bash
  cd sign_language_translator-backend
  python app.py
  ```

### Model Issues

**Error: "isl_model.h5 not found"**
- Verify file exists: `sign_language_translator-backend/ISL_text/isl_model.h5`
- Check disk space (model is ~50MB)

**Error: Out of memory errors**
- Reduce batch size in model configuration
- Close other applications to free RAM

### System Issues

**Error: Python/Node version mismatch**
```bash
# Check versions
python --version    # Should be 3.10+
node --version      # Should be 16+
npm --version       # Should be 8+
```

**Error: "Permission denied" errors (Mac/Linux)**
```bash
chmod +x venv/bin/activate
chmod -R 755 node_modules
```

---

**Still having issues?** Open a GitHub issue with:
- Error message (full traceback)
- Your OS & Python/Node version
- Steps to reproduce

## Future Enhancements

- Real-time video feed processing
- Mobile application support
- Multi-language support (beyond English-ISL)
- Improved model accuracy with more training data
- Cloud-based deployment
- Accessibility improvements

## License

This project is open source and available under the MIT License.

## Contact & Support

For issues, questions, or suggestions, please open an issue on the GitHub repository.

## Acknowledgments

- ISL linguistic research and resources
- OpenCV for computer vision processing
- TensorFlow/Keras community
- React and Node.js communities

---

**Note**: This is a hackathon project. For production use, additional security measures, testing, and optimization are recommended.
