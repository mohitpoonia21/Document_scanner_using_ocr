# Document Scanner Using OCR

**Author:** Mohit Poonia  
**Registration No.:** 24BAI10966  
**Course:** Computer Vision

## About the Project

This project is a command-line document scanner developed in Python. It takes a photograph of a document, detects the document area, corrects its perspective, improves the scanned image, and extracts the text using Optical Character Recognition (OCR).

The project is divided into three main modules:

1. **Preprocessing and Document Detection** – image validation, resizing, edge detection, document detection, perspective correction, and scan enhancement.
2. **OCR Text Extraction** – text recognition using EasyOCR and confidence-based filtering.
3. **Export and Reporting** – saving the processed scan and extracted OCR results in different formats.

## Main Objective

The main objective of this project is to demonstrate how Computer Vision techniques can be combined with OCR to convert a photographed document into a cleaner digital scan and extract its text.

## Functional Modules

### 1. Preprocessing and Document Detection

The preprocessing module prepares the input image before OCR processing.

It performs the following tasks:

- Validates the input image.
- Checks supported image formats.
- Resizes large images when required.
- Performs edge detection.
- Searches for a document-shaped contour.
- Identifies the four document corner points.
- Orders the detected points correctly.
- Applies a four-point perspective transformation.
- Enhances the resulting scanned image.

If a suitable document cannot be detected, the program reports a document-detection error instead of continuing with an invalid image.

### 2. OCR Text Extraction

The OCR module provides an interface to EasyOCR.

It:

- Creates the OCR reader when it is required.
- Supports configurable OCR languages.
- Extracts text from the processed document.
- Stores recognized text lines with confidence values.
- Removes OCR results below the selected confidence threshold.
- Provides the complete extracted text.
- Calculates the average OCR confidence.

If EasyOCR is not installed, the application provides a clear installation message instead of producing an unhandled import error.

### 3. Export and Reporting

The exporter saves the results using the input filename as the base name.

For example, an input file named `notes.jpg` can produce:

```text
notes_scan.png
notes.txt
notes.json
notes.pdf

The application also maintains a pipeline log:

output/pipeline.log
Requirements

The project uses the following technologies:

Python
OpenCV
NumPy
EasyOCR
FPDF2
pytest

Install the required packages using:

pip install -r requirements.txt

EasyOCR may download its model files when it is initialized for the first time. Therefore, an internet connection may be required during the first OCR run.

Running the Application
Process a single image
python -m src.cli --input input/your_document.jpg --output output
Process a directory of images
python -m src.cli --input-dir input --output output
Change the OCR confidence threshold
python -m src.cli --input input/your_document.jpg --output output --min-confidence 0.3
View all available options
python -m src.cli --help

The CLI also provides options for selecting OCR languages and enabling GPU processing.

Project Structure
Document_scanner_using_ocr/
│
├── diagrams/
│   ├── architecture.svg
│   ├── class_diagram.svg
│   ├── sequence_diagram.svg
│   ├── use_case.svg
│   ├── workflow.svg
│   └── README.md
│
├── input/
│
├── output/
│
├── src/
│   ├── __init__.py
│   ├── cli.py
│   ├── exporter.py
│   ├── logger_config.py
│   ├── ocr_engine.py
│   ├── preprocessing.py
│   └── utils.py
│
├── tests/
│   ├── __init__.py
│   ├── test_ocr_engine.py
│   └── test_preprocessing.py
│
├── .gitignore
├── README.md
├── requirements.txt
└── statement.md
System Workflow
Input Image
     ↓
Input Validation
     ↓
Image Resizing / Preprocessing
     ↓
Edge Detection
     ↓
Document Boundary Detection
     ↓
Perspective Transformation
     ↓
Scan Enhancement
     ↓
EasyOCR Text Extraction
     ↓
Confidence Filtering
     ↓
Export Results
     ↓
PNG + TXT + JSON + PDF
Error Handling

The project uses custom exceptions to handle expected problems.

These include:

Invalid image files
Unsupported file types
Document not found
OCR extraction problems

The CLI catches application errors and displays a clear failure message along with a final success/failure summary.

Testing

Automated tests are included for the preprocessing and OCR modules.

Run the tests using:

pytest -q

The current test suite contains 13 tests.

The development test run completed with:

13 passed

The tests cover areas such as:

Image validation
Image resizing
Document point ordering
Perspective transformation
Edge detection
Scan enhancement
OCR confidence filtering
OCR text handling
Average confidence calculation
Empty OCR results

The preprocessing pipeline was also tested using a synthetic document image.

Full OCR execution could not be completed in the development environment because EasyOCR was not installed there and the environment did not have internet access to install the package and its model files. The application was tested to ensure that this situation is handled with a clear error message.

Non-Functional Requirements
Performance

The application should process normal document images within a reasonable amount of time and avoid unnecessary repeated OCR-reader initialization.

Reliability

Expected input, document-detection, and OCR errors should be handled with clear application messages.

Usability

The command-line interface provides understandable arguments and reports whether processing was successful.

Maintainability

The application is divided into separate modules for preprocessing, OCR, exporting, utilities, logging, and CLI control.

Error Handling

Custom application exceptions are used for expected processing failures.

Logging

Important pipeline events are recorded in the output log.

Supported Input Formats

The application supports the following image extensions:

.jpg
.jpeg
.png
.bmp
.tiff

For best results, the complete document should be visible in the photograph.

Output Files

For an input named:

notes.jpg

the exporter can generate:

notes_scan.png
notes.txt
notes.json
notes.pdf

The application also records pipeline activity in:

output/pipeline.log
Limitations

The document detection stage works best when the complete page is visible and the document is reasonably different from its background.

Detection can become less reliable when:

The document is partly outside the image.
The background is complicated.
The document and background have similar appearance.
The image contains significant distortion or poor lighting.

OCR accuracy can also vary depending on:

Image quality
Lighting
Resolution
Font
Selected language
OCR confidence threshold

The current version is a command-line application and does not include a graphical user interface or direct camera capture.

Future Improvements

Possible improvements for future versions include:

Adding a graphical user interface.
Adding camera-based document capture.
Improving document detection for complex backgrounds.
Adding automatic page orientation correction.
Improving batch-processing feedback.
Supporting additional OCR engines.
Improving PDF layout.
Displaying OCR bounding boxes and confidence values visually.
Design Diagrams

The diagrams/ directory contains the following diagrams:

Architecture Diagram
Workflow Diagram
Use Case Diagram
Class/Component Diagram
Sequence Diagram

These diagrams describe the system structure, processing flow, user interaction, software components, and interaction sequence.

Author

Mohit Poonia
Registration No.: 24BAI10966

Academic Project

This project was developed as a Computer Vision academic project demonstrating document detection, image preprocessing, perspective correction, OCR integration, modular programming, testing, logging, and file export.
