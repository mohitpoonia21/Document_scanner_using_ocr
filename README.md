# Document Scanner & OCR Text Extractor

A Computer Vision project that converts document images into clean scanned documents and extracts text using OCR.

**Author:** Mohit Poonia  
**Reg. No.:** 24BAI10966  
**Course:** Computer Vision

## Features

- Detects the document from an image using OpenCV.
- Corrects perspective to create a scanned view.
- Enhances the document for better readability.
- Extracts text using EasyOCR.
- Filters OCR results using confidence scores.
- Exports results as PNG, TXT, JSON and PDF.
- Supports single-image and batch processing.

## Technologies

Python, OpenCV, NumPy, EasyOCR, FPDF2, Pytest

## Project Structure

```text
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

Put a document image inside the input folder:

python -m src.cli --input input/your_document.jpg --output output

For multiple images:

python -m src.cli --input-dir input --output output
Testing
pytest -q

Result: 13 tests passed

Note

The complete OCR stage requires EasyOCR and its model files. During development, OCR wrapper functionality was tested using mocks because the required model/package download was unavailable in the testing environment
Author

Mohit Poonia
Registration No.: 24BAI10966
