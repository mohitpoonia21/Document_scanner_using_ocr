# Document Scanner Using OCR

**Author:** Mohit Poonia  
**Registration No.:** 24BAI10966  
**Course:** Computer Vision

## About the project

This project is a small command-line document scanner made in Python. The idea is to take a photograph of a document, find the document area, straighten it, improve the image, and then read the text from it using OCR.

I divided the project into three parts:

1. **Preprocessing** – image validation, resizing, edge detection, document detection, perspective correction, and scan enhancement.
2. **OCR** – text recognition with EasyOCR and confidence filtering.
3. **Export** – saving the scan and OCR results as PNG, TXT, JSON, and PDF.

## Main objective

The main objective is to demonstrate how common Computer Vision techniques can be combined with OCR to turn a photographed document into a cleaner digital copy with extracted text.

## Functional modules

### 1. Preprocessing and document detection

The preprocessing module works on the input image before OCR is called. It:

- checks whether the input file is valid;
- resizes large images when needed;
- creates an edge image;
- looks for a document-shaped contour;
- orders the four detected corner points;
- applies a four-point perspective transform;
- enhances the resulting scan.

If a suitable document cannot be found, the program reports a document-detection error instead of continuing with an invalid image.

### 2. OCR text extraction

The OCR module is an EasyOCR wrapper. It:

- creates the OCR reader only when it is needed;
- accepts configurable languages;
- removes results below the selected confidence value;
- stores each recognized line with its confidence;
- provides the combined text and average confidence.

If EasyOCR is unavailable, the application gives an installation message instead of showing an unhandled import traceback.

### 3. Export and reporting

The exporter saves the result using the input filename as the base name.

For example, an input called `notes.jpg` can produce:

```text
notes_scan.png
notes.txt
notes.json
notes.pdf
