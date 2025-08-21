
# 📄 PDF Extraction Using Python

This repository contains a Google Colab notebook demonstrating **PDF text and data extraction** using three popular Python libraries:

- [`pypdf`](https://pypdf.readthedocs.io/en/stable/) → Extracts text from PDF pages.
- [`pdfplumber`](https://github.com/jsvine/pdfplumber) → Extracts structured data such as tables.
- [`PyMuPDF (fitz)`](https://pymupdf.readthedocs.io/en/latest/) → Extracts text, metadata, images, and links.

---

## ⚙️ Installation

To run the notebook in Google Colab or locally, install the dependencies:

```bash
pip install pypdf pdfplumber pymupdf
```

---

## 📑 Features in the Notebook

1. **Using pypdf**
   - Open PDF files
   - Count pages
   - Extract text page by page

   ```python
   from pypdf import PdfReader
   reader = PdfReader("file02.pdf")
   for page in reader.pages:
       print(page.extract_text())
   ```

2. **Using pdfplumber**
   - Open PDF
   - Extract tables

   ```python
   import pdfplumber
   with pdfplumber.open("file02.pdf") as f:
       for page in f.pages:
           print(page.extract_tables())
   ```

3. **Using PyMuPDF (fitz)**
   - Open PDF
   - Get metadata
   - Extract text from a page
   - Save a page as an image (`.png`)
   - Extract links from a page

   ```python
   import fitz
   doc = fitz.open("file02.pdf")
   page = doc.load_page(7)
   print(page.get_text())
   pix = page.get_pixmap()
   pix.save("page_7.png")
   print(page.get_links())
   ```

---

## 📂 Files

- `pdf_extraction.ipynb` → The main Google Colab notebook
- `README.md` → Documentation for the project

---

## 🚀 Usage

1. Upload your PDF file (e.g., `file02.pdf`) to Colab or your local directory.
2. Run each section to see extraction results.
3. Modify the page numbers or methods depending on your PDF file.

---

## 🔮 Future Improvements

- Add OCR support for scanned PDFs using `pytesseract`.
- Add structured JSON export for extracted text and tables.
- Build a simple UI to upload and parse PDFs.

---

## 📝 Author
- **Navya Achanti**  
  Repository: [Pdf-Extraction-Using-Python](https://github.com/Navyaaa2708/Pdf-Extraction-Using-Python)
