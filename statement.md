# Project Statement

## Document Scanner & OCR Text Extractor

**Author:** Mohit Poonia  
**Registration No.:** 24BAI10966  
**Domain:** Computer Vision

## Problem Statement

Photographs of documents often contain perspective distortion, uneven lighting, background noise, and other visual imperfections. These issues make it difficult to directly use the photograph as a clean digital document or reliably extract its text.

The proposed project addresses this problem by developing a Document Scanner & OCR Text Extractor using Python, OpenCV, and EasyOCR. The system detects the document region in an image, corrects its perspective, enhances the resulting scan, extracts text using OCR, and exports the results into common digital formats.

## Proposed Solution

The system is organized into three functional modules.

### Module 1 — Image Preprocessing and Document Detection

The first module accepts and validates an image, prepares it for computer-vision processing, detects document-like boundaries, identifies the document corners, and applies a four-point perspective transformation. The resulting document is enhanced to provide a cleaner image for OCR.

### Module 2 — OCR Text Extraction

The second module uses EasyOCR to recognize text from the processed document. OCR results are filtered using a configurable minimum confidence threshold. The module provides recognized text lines, confidence information, complete extracted text, and average confidence.

### Module 3 — Export and Reporting

The third module stores the results in multiple formats. The processed scan is saved as an image, extracted text is saved as TXT, OCR information is stored as JSON, and a PDF report is generated. Pipeline logging is also maintained for execution monitoring and troubleshooting.

## Functional Requirements

**FR1: Document Detection and Preprocessing**  
The system shall validate the input image, preprocess it, detect the document boundary, correct perspective, and enhance the scanned result.

**FR2: OCR Text Extraction**  
The system shall extract text using EasyOCR, support configurable languages, filter results by confidence, and provide OCR confidence information.

**FR3: Export and Reporting**  
The system shall export the processed scan and OCR results as PNG, TXT, JSON, and PDF files and maintain pipeline logs.

## Non-Functional Requirements

- **Performance:** The system should process normal document images efficiently.
- **Reliability:** Expected input, document-detection, and OCR errors should be handled clearly.
- **Usability:** CLI arguments and output messages should be understandable.
- **Maintainability:** Functions are separated into modules according to their responsibilities.
- **Error Handling:** Application-specific exceptions are used for expected failures.
- **Logging:** Important pipeline events are recorded in the output log.

## Technology Stack

| Component | Technology |
|---|---|
| Programming Language | Python |
| Computer Vision | OpenCV |
| Numerical Processing | NumPy |
| OCR | EasyOCR |
| PDF Generation | FPDF2 |
| Testing | pytest |
| Interface | Command Line Interface |

## Expected Input

The system accepts common image formats supported by the implementation, including:

- JPG
- JPEG
- PNG
- BMP
- TIFF

The input should contain a document that is sufficiently visible for the document-detection stage.

## Expected Output

A successful run produces:

- Perspective-corrected scan image
- Extracted TXT file
- OCR JSON file
- PDF output
- Pipeline log

## Testing and Verification

The project includes automated tests for the preprocessing and OCR modules. The recovered test suite contains 13 tests, and all 13 tests pass in the development environment.

The preprocessing stage has also been tested using a synthetic document image. Full OCR execution requires EasyOCR and its model files to be available in the execution environment.

## Design

The project uses a modular architecture:

```text
CLI
 │
 ├── Preprocessing / Document Detection
 │
 ├── OCR Engine
 │
 └── Exporter
       │
       └── Output Files
```

Supporting components include utilities for validation and directory handling and centralized logging for pipeline events.

## Scope

The project focuses on document scanning and text extraction from image inputs. It is intended as an academic Computer Vision project demonstrating image preprocessing, contour-based document detection, perspective transformation, OCR, modular software design, testing, and result export.

## Future Scope

Possible improvements include a graphical user interface, stronger document detection under difficult backgrounds, automatic orientation correction, additional OCR engines, batch-processing support, and improved searchable-PDF generation.

## Declaration

I, **Mohit Poonia**, Registration No. **24BAI10966**, submit this project as an academic implementation of a Computer Vision based Document Scanner & OCR Text Extractor.

**Name:** Mohit Poonia  
**Registration No.:** 24BAI10966

**Date:** ____________________

**Signature:** ____________________
