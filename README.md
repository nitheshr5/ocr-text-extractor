# OCR to JSON Web App

A simple web application that extracts text from uploaded images or PDFs using OCR (Tesseract) and returns it as JSON. Built with a Flask backend and a modern frontend (React or static HTML).

---

## 🚀 Features

- Upload image or PDF files
- Extract text using Tesseract OCR
- Return structured JSON output
- CORS-enabled backend for cross-origin requests
- Support for multiple file formats: PNG, JPG, JPEG, and PDF
- Clean, modern web interface
- Real-time text extraction processing

---

## 🛠 Tech Stack

- **Backend**: Python, Flask, pytesseract, pdf2image, Pillow
- **Frontend**: HTML/CSS/JavaScript (or React app placed in `frontend/`)
- **OCR Engine**: Tesseract OCR
- **PDF Support**: Poppler (via `pdf2image`)
- **File Handling**: Flask file upload with validation

---

## 📦 Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/nitheshr5/ocr-to-json-web-app.git
cd ocr-to-json-web-app
```

### 2. Set up Virtual Environment (Recommended)
```bash
cd backend
python -m venv venv

# On Windows
venv\Scripts\activate

# On macOS/Linux
source venv/bin/activate
```

### 3. Install Python Dependencies
```bash
pip install -r requirements.txt
```

Or install manually:
```bash
pip install flask flask-cors pytesseract pdf2image pillow
```

---

## 📂 Project Structure

```
ocr_to_json_web_app/
├── backend/
│   ├── main.py                  # Flask application entry point
│   ├── requirements.txt         # Python dependencies
│   ├── uploads/                 # Temporary file storage
│   └── venv/                    # Virtual environment
├── frontend/
│   └── index.html               # Frontend entry file
├── README.md
└── .gitignore
```

---

## ⚙️ Prerequisites

### 1. Install Tesseract OCR

**Windows:**
- Download from: https://github.com/tesseract-ocr/tesseract/wiki
- Add installation path to system environment variables (e.g., `C:\Program Files\Tesseract-OCR`)

**macOS:**
```bash
brew install tesseract
```

**Ubuntu/Debian:**
```bash
sudo apt-get install tesseract-ocr
```

### 2. Install Poppler (For PDF Support)

**Windows:**
- Download binaries from: https://blog.alivate.com.au/poppler-windows/
- Extract and add the `bin/` folder to your system PATH

**macOS:**
```bash
brew install poppler
```

**Ubuntu/Debian:**
```bash
sudo apt-get install poppler-utils
```

---

## 🚀 Running the Application

### Start the Backend Server
From the `backend/` directory:
```bash
python main.py
```

The server will start on: `http://127.0.0.1:5000`

### Access the Frontend
Open your browser and navigate to: `http://127.0.0.1:5000`

---

## 📤 API Documentation

### POST /upload

**Description:** Upload an image or PDF file and receive extracted text in JSON format.

**Request:**
- **Method:** POST
- **Content-Type:** multipart/form-data
- **Body:** 
  - `file`: Image file (PNG, JPG, JPEG) or PDF file

**Response:**
```json
{
  "extracted_text": "Your extracted text content will appear here..."
}
```

**Error Response:**
```json
{
  "error": "Error message describing what went wrong"
}
```

---

## 🧪 Testing the API

### Using cURL
```bash
curl -X POST -F "file=@example.pdf" http://127.0.0.1:5000/upload
```

### Using the Web Interface
1. Navigate to `http://127.0.0.1:5000`
2. Click "Choose File" and select an image or PDF
3. Click "Extract Text"
4. View the extracted text in JSON format

---

## 🌐 Production Deployment Notes

### Local Storage Limitation
By default, uploaded files are temporarily saved in the local `uploads/` folder, which is not suitable for production environments.

### Recommended Production Setup:
- **Frontend Hosting:** Firebase Hosting, Netlify, or Vercel
- **Backend Deployment:** Google Cloud Run, Heroku, or Render
- **File Storage:** Firebase Storage, AWS S3, or Google Cloud Storage
- **Database:** Consider adding a database for storing extraction history
- **Authentication:** Implement user authentication for secure access

### Environment Variables for Production:
```bash
FLASK_ENV=production
TESSERACT_CMD=/usr/bin/tesseract  # Path to tesseract executable
UPLOAD_FOLDER=/tmp/uploads        # Temporary file storage path
MAX_CONTENT_LENGTH=16777216       # 16MB file size limit
```

---

## ✅ Future Enhancements

- [ ] Direct upload to cloud storage (Firebase Storage/AWS S3)
- [ ] User authentication and session management
- [ ] Download/export extracted text as various formats
- [ ] Batch processing for multiple files
- [ ] React.js frontend integration
- [ ] Text extraction confidence scores
- [ ] Support for additional file formats (TIFF, BMP)
- [ ] OCR language selection
- [ ] Text post-processing and formatting options
- [ ] Extraction history and user dashboard

---

## 🐛 Troubleshooting

### Common Issues:

**1. Tesseract not found error:**
- Ensure Tesseract is installed and added to system PATH
- On Windows, check environment variables

**2. PDF processing fails:**
- Verify Poppler is installed and accessible
- Check if PDF is not password-protected

**3. Large file upload issues:**
- Check Flask's MAX_CONTENT_LENGTH setting
- Ensure sufficient disk space in uploads folder

**4. CORS errors:**
- Verify flask-cors is installed and configured
- Check if frontend and backend URLs match

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 🧑‍💻 Author

**Ranjith V**
- GitHub: https://github.com/nitheshr5
- Email: nitheshrpoojari5@gmail.com

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- [Tesseract OCR](https://github.com/tesseract-ocr/tesseract) for the OCR engine
- [Flask](https://flask.palletsprojects.com/) for the web framework
- [pdf2image](https://github.com/Belval/pdf2image) for PDF processing
- [Pillow](https://pillow.readthedocs.io/) for image processing

---

**⭐ If you found this project helpful, please give it a star!**