# fake-screenshot-detection
FakeShield uses 4 detection layers for fake screenshot analysis: ELA finds edited regions via compression errors, OCR validates transaction text patterns, metadata forensics checks EXIF/editing traces, and a MobileNetV2 CNN detects manipulation artifacts in screenshots for a final authenticity verdict.
# FakeShield — Financial Screenshot Detector

FakeShield is an AI-powered multi-modal forensic system designed to detect manipulated financial transaction screenshots from platforms like EasyPaisa, JazzCash, and similar digital payment services.

The system combines image forensics, OCR validation, metadata analysis, and deep learning to provide a comprehensive authenticity verdict.

---

# 🚀 Features

* Detects edited or tampered financial screenshots
* Supports EasyPaisa, JazzCash, and similar transaction receipts
* Multi-layer forensic analysis pipeline
* AI-powered CNN detection using MobileNetV2
* Visual heatmap generation for suspicious regions
* OCR-based transaction validation
* Metadata and EXIF inspection
* Lightweight frontend with Python backend

---

# 📦 Project Structure

```bash
FakeShield/
│
├── backend/              # Flask/FastAPI backend
├── frontend/             # Web interface
├── training/             # CNN training scripts
├── data/
│   ├── real/             # Genuine screenshots
│   └── fake/             # Manipulated screenshots
│
└── README.md
```

---

# ⚡ Quick Start

## 1. Prerequisites

Make sure you have the following installed:

* Python 3.9 or higher
* pip
* Tesseract OCR *(optional but recommended)*

### Install Tesseract OCR

* Windows: Install from official Tesseract builds
* Linux:

```bash
sudo apt install tesseract-ocr
```

---

# 🔧 Backend Setup

```bash
cd backend

python -m venv venv
```

### Activate Virtual Environment

#### Windows

```bash
.\venv\Scripts\activate
```

#### Linux/Mac

```bash
source venv/bin/activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Run Backend Server

```bash
python main.py
```

Server will start at:

```bash
http://127.0.0.1:8000
```

---

# 🌐 Frontend Setup

Simply open:

```bash
frontend/index.html
```

in any modern web browser.

---

# 🛠️ Detection Pipeline

FakeShield uses four independent forensic layers to analyze screenshots:

## 1. Error Level Analysis (ELA)

* Re-compresses the uploaded image
* Calculates pixel-level compression differences
* Highlights suspicious edited regions through heatmaps

## 2. OCR Pattern Validation

Extracted text is validated against common financial transaction patterns such as:

* Amount formats
* Transaction IDs
* Date and time formats
* Sender/receiver structures

## 3. Metadata Forensics

Analyzes EXIF metadata for:

* Editing software traces
* Timestamp inconsistencies
* Missing or altered metadata

Common tools detected include:

* Photoshop
* GIMP
* Snapseed

## 4. Deep Learning CNN

A MobileNetV2-based classifier trained to detect:

* Screenshot manipulation artifacts
* Synthetic editing traces
* Compression inconsistencies

---

# 🏋️ Training Your Own Model

You can improve the CNN detector using your own dataset.

## Step 1 — Add Dataset

Place screenshots inside:

```bash
data/real/
data/fake/
```

---

## Step 2 — Generate Synthetic Fake Data (Optional)

```bash
cd training

python augment.py --input_dir ../data/real --output_dir ../data/fake --count 200
```

---

## Step 3 — Train the Model

```bash
python train.py --data_dir ../data --epochs 20
```

---

# 💾 Model Output

The trained model will automatically be saved to:

```bash
backend/models/mobilenet_detector.keras
```

---

# 📊 Future Improvements

* Real-time screenshot verification
* GAN-based forgery detection
* Support for banking applications
* Blockchain verification integration
* Mobile app deployment

---

# ⚠️ Disclaimer

FakeShield is intended for educational, research, and forensic analysis purposes only.

No automated detection system is 100% accurate. Always perform manual verification before making critical financial or legal decisions.

---

# 📄 License

This project is open-source and available under the MIT License.
project link: https://drive.google.com/file/d/1w8lDqehrJ-2QhN_LWahgcjXLzK2oBgr8/view?usp=sharing 
the project file is very big in so this is the link of google drive 
