# Document Scanner & OCR Text Extractor

A Computer Vision project that converts document images into clean scanned documents and extracts text using OCR.

**Author:** Mohit Poonia  
**Registration No.:** 24BAI10966  
**Course:** Computer Vision

## Features

- Detects documents from images using OpenCV.
- Corrects perspective and enhances the scanned document.
- Extracts text using EasyOCR.
- Filters OCR results using confidence scores.
- Exports results as PNG, TXT, JSON and PDF.
- Supports single-image and batch processing.

## Technologies

Python, OpenCV, NumPy, EasyOCR, FPDF2, Pytest

## Project Structure

Document_scanner_using_ocr/
├── diagrams/
├── input/
├── output/
├── src/
├── tests/
├── README.md
├── requirements.txt
└── statement.md
Setup
git clone https://github.com/mohitpoonia21/Document_scanner_using_ocr.git
cd Document_scanner_using_ocr
pip install -r requirements.txt
Run

Place a document image inside the input folder and run:

python -m src.cli --input input/your_document.jpg --output output

For multiple images:

python -m src.cli --input-dir input --output output
Testing
pytest -q

Result: 13 tests passed

Output

The application can generate:

document_scan.png
document.txt
document.json
document.pdf
Note

The complete OCR stage requires EasyOCR and its model files. During development, the OCR wrapper was tested using mocks because the required package/model download was unavailable in the testing environment.
