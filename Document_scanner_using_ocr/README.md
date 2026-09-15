# Document Scanner & OCR Text Extractor

**Author:** Mohit Poonia  
**Registration No.:** 24BAI10966  
**Course Domain:** Computer Vision

## 1. Project Overview

Document Scanner & OCR Text Extractor is a Python-based Computer Vision project that detects a document in an input photograph, corrects its perspective, extracts text using Optical Character Recognition (OCR), and exports the processed results into useful file formats.

The project is designed as a command-line application and is organized into three main functional modules:

1. **Image Preprocessing and Document Detection**
2. **OCR Text Extraction**
3. **Export and Reporting**

## 2. Objectives

- Detect a document/page from a photograph.
- Correct perspective distortion to produce a flattened scan.
- Improve the image for OCR processing.
- Extract text using EasyOCR.
- Export the scanned image and extracted text.
- Provide TXT, JSON, and PDF outputs.
- Provide logging and clear error handling.

## 3. Functional Requirements

### FR1 — Document Detection and Preprocessing
The system shall:
- Accept supported image files.
- Validate the input image path and extension.
- Resize images for processing when required.
- Convert/process the image for edge detection.
- Detect a document-like four-corner contour.
- Apply a four-point perspective transformation.
- Enhance the resulting scan for OCR.

### FR2 — OCR Text Extraction
The system shall:
- Use EasyOCR for text recognition.
- Support configurable OCR languages.
- Apply a minimum confidence threshold.
- Return recognized text lines and confidence scores.
- Calculate the complete extracted text and average confidence.
- Report an OCR error when usable text cannot be extracted.

### FR3 — Export and Reporting
The system shall:
- Save the processed scan image.
- Save extracted text as a TXT file.
- Save OCR information as JSON.
- Generate a PDF containing the scan and extracted text.
- Create the output directory when required.

## 4. Non-Functional Requirements

### Performance
The system should process normal document images efficiently and avoid unnecessary repeated OCR-reader initialization.

### Reliability
Invalid files, missing documents, and OCR failures should be handled without terminating the application with an uncontrolled traceback.

### Usability
The command-line interface should provide clear arguments, progress information, success/failure status, and a final summary.

### Maintainability
The implementation is divided into separate modules for preprocessing, OCR, exporting, utilities, logging, and CLI orchestration.

### Error Handling
The project defines application-specific errors for invalid files, missing documents, and OCR extraction problems.

### Logging
Pipeline events are logged to the output log file and also reported through the console logging system.

## 5. Technology Stack

- **Language:** Python
- **Computer Vision:** OpenCV
- **Numerical Processing:** NumPy
- **OCR:** EasyOCR
- **PDF Generation:** FPDF2
- **Testing:** pytest
- **Interface:** Command Line Interface (CLI)

## 6. Project Structure

```text
document-scanner-ocr/
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
├── input/
├── output/
├── diagrams/
├── requirements.txt
├── README.md
└── statement.md
```

## 7. Installation

Clone the repository and move into the project directory.

Install the dependencies:

```bash
pip install -r requirements.txt
```

EasyOCR may download its required recognition models the first time it is initialized. An internet connection may therefore be required during the first OCR run.

## 8. Running the Application

### Process one image

```bash
python -m src.cli --input input/sample_document_test.png --output output
```

### Set OCR confidence threshold

```bash
python -m src.cli --input input/sample_document_test.png --output output --min-confidence 0.3
```

### Process a directory of images

```bash
python -m src.cli --input-dir input --output output
```

### View CLI options

```bash
python -m src.cli --help
```

The CLI also supports OCR language and GPU configuration through its command-line arguments.

## 9. Output Files

For a successfully processed image, the exporter creates files based on the input filename:

```text
<name>_scan.png
<name>.txt
<name>.json
<name>.pdf
```

A pipeline log is also maintained in:

```text
output/pipeline.log
```

## 10. Testing

The project contains automated tests for preprocessing and OCR behavior.

Run:

```bash
pytest -q
```

The recovered test suite currently contains **13 tests**, covering:
- image validation,
- image resizing,
- point ordering,
- perspective transformation,
- edge detection,
- scan enhancement,
- OCR confidence filtering,
- empty/no-text OCR behavior,
- extracted full text,
- average OCR confidence.

## 11. System Workflow

```text
Input Image
     ↓
Validate Image
     ↓
Resize / Preprocess
     ↓
Edge Detection
     ↓
Document Contour Detection
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
```

## 12. Error Handling

The application uses custom exceptions to represent expected failures, including invalid image files, missing documents, and OCR extraction problems.

If EasyOCR is not installed, the application reports an actionable installation message instead of exposing an uncontrolled module-import traceback.

## 13. Current Verification

The automated unit test suite has been verified with:

```text
13 passed
```

The Computer Vision preprocessing stage has also been exercised with a synthetic document image. Full OCR execution depends on EasyOCR and its recognition models being available in the execution environment.

## 14. Limitations

- Document detection works best when the complete document is visible and reasonably separated from the background.
- OCR accuracy depends on image quality, lighting, font, language selection, and the EasyOCR model.
- EasyOCR model files may need to be downloaded on first use.
- The current application is command-line based and does not provide a graphical user interface.

## 15. Future Enhancements

- Add a graphical user interface.
- Support batch-processing progress indicators.
- Add automatic image rotation/orientation correction.
- Improve document detection for complex backgrounds.
- Add more OCR engines or configurable OCR backends.
- Improve PDF generation with text positioned directly over the scanned document.
- Add confidence visualization and OCR bounding-box visualization.

## 16. Author

**Mohit Poonia**  
**Registration No.: 24BAI10966**
