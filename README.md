# Document Scanner Using OCR

**Author:** Mohit Poonia  
**Registration No.:** 24BAI10966  
**Course:** Computer Vision

## About the Project

Document Scanner Using OCR is a Python-based Computer Vision project that converts a photograph of a document into a cleaner scanned image and extracts its text using OCR.

The project uses **OpenCV** for image processing and document detection and **EasyOCR** for text extraction.

## Main Features

- Validate input image files.
- Detect the document from an image.
- Detect document corners and correct perspective.
- Enhance the scanned document.
- Extract text using EasyOCR.
- Filter OCR results using confidence values.
- Export results as PNG, TXT, JSON, and PDF.
- Maintain a pipeline log.
- Include automated tests using pytest.

## Project Modules

### Module 1 — Preprocessing

This module prepares the input image for OCR. It performs image validation, resizing, edge detection, document detection, perspective transformation, and scan enhancement.

### Module 2 — OCR

This module uses EasyOCR to recognize text from the processed document. It supports configurable languages and confidence filtering.

### Module 3 — Export

This module saves the processed scan and extracted OCR information in different formats:

```text
<name>_scan.png
<name>.txt
<name>.json
<name>.pdf
Technologies Used
Technology	Purpose
Python	Main programming language
OpenCV	Image processing and document detection
NumPy	Numerical operations
EasyOCR	Text extraction
FPDF2	PDF generation
pytest	Testing
Project Structure
Document_scanner_using_ocr/
├── diagrams/
├── input/
├── output/
├── src/
│   ├── __init__.py
│   ├── cli.py
│   ├── exporter.py
│   ├── logger_config.py
│   ├── ocr_engine.py
│   ├── preprocessing.py
│   └── utils.py
├── tests/
│   ├── __init__.py
│   ├── test_ocr_engine.py
│   └── test_preprocessing.py
├── .gitignore
├── README.md
├── requirements.txt
└── statement.md
Installation

Install the required packages:

pip install -r requirements.txt

EasyOCR may need to download its model files during the first OCR run.

Running the Project

For a single image:

python -m src.cli --input input/your_document.jpg --output output

For multiple images:

python -m src.cli --input-dir input --output output

To view the available options:

python -m src.cli --help
Testing

Run:

pytest -q

The current test suite contains 13 tests, with the development test run completing successfully:

13 passed

The tests cover preprocessing functions and OCR result handling.

Design Diagrams

The diagrams/ folder contains:

Architecture Diagram
Workflow Diagram
Use Case Diagram
Class/Component Diagram
Sequence Diagram
Limitations

The document detector works best when the complete page is visible and clearly separated from the background. OCR accuracy can vary depending on image quality, lighting, language, and text size.

The current version is a command-line application and does not include a GUI or direct camera capture.

Future Scope

Possible improvements include a GUI, automatic page rotation, better detection for complex backgrounds, additional OCR engines, and improved PDF formatting.

Author

Mohit Poonia
Registration No.: 24BAI10966
