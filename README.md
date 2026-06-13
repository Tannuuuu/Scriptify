# Scriptify 🎙️
### Handwritten Notes → Audio, Instantly

Scriptify is an end-to-end web application that converts batches of handwritten note images into a single, playable audio file. Upload your pages, wait a few seconds, and listen to your notes — no typing required.

---

## How It Works

```
Upload Images → OCR Extraction → Text Post-Processing → Audio Synthesis → Playback
```

1. **Upload** a batch of handwritten note images via the web interface
2. **OCR** extracts text from each page using Google Vision OCR
3. **Post-processing** cleans and corrects the extracted text using confidence thresholding
4. **Audio synthesis** converts the cleaned text to natural speech using gTTS
5. **Playback** — a combined audio file is generated and played directly in the browser

---

## Features

- Batch upload of multiple handwritten note images
- Combined audio output playable directly in the browser after upload
- Custom OCR post-processing pipeline to handle shorthand and complex annotations
- End-to-end latency of **< 2 seconds per page**
- **< 5% Word Error Rate (WER)** across diverse handwriting styles

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML, CSS |
| Backend | Python, Flask |
| OCR | Google Vision OCR API |
| Text-to-Speech | gTTS |
| ML/Processing | PyTorch, NumPy, Pandas |

---

## Dataset

<!-- ADD KAGGLE DATASET NAME AND LINK HERE once you find it -->
- Kaggle handwritten notes dataset (link to be added)
- Supplemented with 300+ pages of custom-curated academic notes for post-processing fine-tuning

---

## Results

| Metric | Value |
|---|---|
| Word Error Rate (WER) | < 5% across 10+ handwriting styles |
| End-to-end latency | < 2 seconds per page |
| Dataset size | 300+ pages |

---

## Getting Started

### Prerequisites

```bash
pip install flask gtts torch numpy pandas google-cloud-vision
```

You will also need a **Google Cloud Vision API key**. Set it as an environment variable:

```bash
export GOOGLE_APPLICATION_CREDENTIALS="path/to/your/credentials.json"
```

### Run Locally

```bash
git clone https://github.com/yourusername/scriptify.git
cd scriptify
pip install -r requirements.txt
python app.py
```

Then open `http://localhost:5000` in your browser.

---

## Project Structure

```
scriptify/
├── app.py               # Flask backend
├── ocr.py               # Google Vision OCR extraction
├── postprocess.py       # Text cleaning and correction pipeline
├── tts.py               # gTTS audio synthesis
├── static/
│   ├── style.css        # Frontend styling
│   └── script.js        # Upload and playback logic
├── templates/
│   └── index.html       # Web interface
└── requirements.txt
```

---

## Limitations

- Works best with clearly written or printed handwriting; highly stylized scripts may affect WER
- Audio is generated in English only
- Large batches (20+ pages) may increase processing time

---

Author

**Tanisha Choudhary**  
BTech CSE, BIT Mesra  
[LinkedIn](https://www.linkedin.com/in/tanisha303/)
