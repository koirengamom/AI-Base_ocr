# AI-Based OCR System

A Python-based Optical Character Recognition (OCR) application that extracts text from images and PDF documents using PaddleOCR. The system supports multiple languages, table detection, document formatting, and export to TXT and DOCX formats through an interactive Streamlit web interface.

---

## Features

* Extract text from images (JPG, JPEG, PNG, BMP, TIFF)
* Extract text from PDF documents
* Multi-language OCR support using PaddleOCR
* Automatic image preprocessing
* Table detection and reconstruction
* Export extracted text to TXT format
* Export extracted text to DOCX format
* User-friendly Streamlit web interface
* Confidence score calculation for OCR results

---

## Project Structure

```text
AI-Base_ocr/
│
├── streamlit_app.py       # Streamlit frontend
├── ocr_engine.py          # OCR processing engine
├── preprocess.py          # Image preprocessing
├── pdf_handler.py         # PDF page handling
├── table_detector.py      # Table detection logic
├── output_writer.py       # TXT and DOCX generation
│
├── requirements.txt
├── README.md
│
└── assets/
```

---

## System Workflow

```text
Input Image/PDF
       │
       ▼
Preprocessing
(Resize, Grayscale, Denoise)
       │
       ▼
PaddleOCR
(Text Detection & Recognition)
       │
       ▼
Table Detection
       │
       ▼
Text Formatting
       │
       ▼
TXT / DOCX Output
       │
       ▼
Display in Streamlit
```

---

## Prerequisites

### Linux (Ubuntu/Debian)

Install required system packages:

```bash
sudo apt update

sudo apt install -y \
    libgl1 \
    poppler-utils
```

### Package Description

| Package       | Purpose                                 |
| ------------- | --------------------------------------- |
| libgl1        | Required by OpenCV for image processing |
| poppler-utils | Required for PDF-to-image conversion    |
| python3-venv  | Create virtual environments             |

---

## Python Version

Recommended:

```text
Python 3.10+
```

---

## Installation

### 1. Clone Repository

```bash
git clone https://github.com/your-username/AI-Base_ocr.git

cd AI-Base_ocr
```

### 2. Create Virtual Environment

```bash
python -m venv .venv
```

### 3. Activate Virtual Environment

Linux/macOS:

```bash
source .venv/bin/activate
```

Windows:

```cmd
.venv\Scripts\activate
```

### 4. Install Python Dependencies

```bash
pip install --upgrade pip

pip install -r requirements.txt
```

If requirements.txt is unavailable:

```bash
pip install streamlit

pip install paddleocr

pip install paddlepaddle

pip install opencv-python

pip install numpy

pip install pillow

pip install pdf2image

pip install python-docx
```

---

## Running the Application

Start the Streamlit server:

```bash
streamlit run streamlit_app.py
```

The application will open automatically in your browser.

Default URL:

```text
http://localhost:8501
```

---

## Supported Input Formats

### Images

* JPG
* JPEG
* PNG
* BMP
* TIFF

### Documents

* PDF

---

## Output Formats

### TXT

Plain text output containing extracted content.

### DOCX

Formatted Microsoft Word document containing:

* Extracted paragraphs
* Reconstructed tables
* OCR results

---

## OCR Engine

The project uses PaddleOCR for:

* Text Detection
* Text Recognition
* Multi-language OCR

Supported languages include:

* English
* Hindi
* Chinese
* French
* German
* Spanish
* Arabic
* And many others supported by PaddleOCR

---

## Image Preprocessing

Before OCR, images undergo:

1. Image Loading
2. Resizing
3. Grayscale Conversion
4. Noise Removal
5. Thresholding (optional)
6. RGB Conversion

These steps improve OCR accuracy and reduce processing time.

---

## PDF Processing

PDF files are processed as follows:

```text
PDF
 │
 ▼
Convert Pages to Images
 │
 ▼
OCR on Each Page
 │
 ▼
Merge Results
 │
 ▼
Generate Output
```

The project uses Poppler through pdf2image for PDF rendering.

---

## Table Detection

The system identifies table structures by:

* Grouping OCR text into rows
* Detecting column alignment
* Reconstructing tables
* Exporting formatted tables into DOCX and TXT

---

## Example Usage

1. Upload an image or PDF.
2. Select OCR language.
3. Click Process.
4. Review extracted text.
5. Download TXT or DOCX output.

---

## Troubleshooting

### Error: libGL.so.1 not found

Install:

```bash
sudo apt install libgl1
```

### Error: Poppler not installed

Install:

```bash
sudo apt install poppler-utils
```

### PaddleOCR Model Download Issues

Update pip and reinstall PaddleOCR:

```bash
pip install --upgrade pip

pip install --upgrade paddleocr paddlepaddle
```

---

## Future Enhancements

* Handwritten text recognition
* Layout analysis
* OCR result highlighting
* Searchable PDF generation
* Batch processing
* Cloud deployment

---

## Author

Developed as part of an OCR System Development Project using Python, Streamlit, OpenCV, PDF2Image, and PaddleOCR.
