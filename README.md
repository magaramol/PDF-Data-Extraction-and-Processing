

# PDF Data Extraction from MHA Website Using Camelot & PDFplumber

This project automates the process of downloading PDF files from the Ministry of Home Affairs (MHA) website and extracting structured data from them. Using **Camelot** and **PDFplumber**, the script handles both table and text extraction, providing a structured output for further analysis.

## Project Overview

The project is divided into two primary tasks:
1. **Table Extraction using Camelot**: This feature focuses on extracting tabular data from the PDFs.
2. **Text Extraction using PDFplumber**: This feature extracts simple text, particularly from the first page of the PDFs.

---

### **Camelot-Based Table Extraction**

#### Features
- **Table Extraction**: Extracts tables from PDFs containing structured data and converts them into a pandas dataframe.
- **Data Organization**: Cleans and organizes the extracted table data into a dictionary format for easy analysis.

#### Workflow
1. **Download PDFs**: Automatically downloads PDF files from the MHA website using `requests` and `BeautifulSoup`.
2. **Extract Tables**: Utilizes **Camelot** to extract tables from the PDFs.
3. **Data Combination**: The extracted table data is combined into a structured format (e.g., a pandas dataframe) for further processing and analysis.

#### Sample Output
The table data extracted from the PDFs will be in a structured format, like:

```python
{
    "title": "List of Unlawful Associations...",
    "data": [
        {"sr_no": "1", "Name_of_Association": "ABC Organization"},
        {"sr_no": "2", "Name_of_Association": "XYZ Organization"},
        ...
    ]
}
```

---

### **PDFplumber-Based Text Extraction**

#### Features
- **Text Extraction**: Extracts text from the first page of each PDF, where titles and introductory content are typically located.
- **Data Storage**: Stores the extracted text in a dictionary format for easy access and further analysis.

#### Workflow
1. **Download PDFs**: Scrapes the MHA website for PDF links using `BeautifulSoup` and downloads the files using `requests`.
2. **Extract Text**: Employs **PDFplumber** to extract text content from the first page of each PDF.
3. **Data Organization**: Saves the extracted text in a structured format, such as a dictionary.

#### Sample Output
The text extracted from the first page of each PDF will be stored in the following format:

```python
{
    "title": "List of Terrorists...",
    "data": {
        "Page_1": "This is the extracted text from the first page..."
    }
}
```

---

## Setup & Installation

To run this project, ensure the following Python libraries are installed:

```bash
pip install requests pdfplumber camelot-py beautifulsoup4 lxml pandas ghostscript
```

Additional system dependencies such as **Ghostscript** are required for **Camelot** to work properly.

---

## How It Works

1. **Download PDFs**: The script automatically downloads the PDFs from the MHA website.
2. **Extract Data**: 
   - Tables are extracted using **Camelot** and stored in a pandas dataframe.
   - Text is extracted using **PDFplumber** and stored in a dictionary format.
3. **Store & Organize**: The extracted data (tables and text) are organized and stored for further analysis.

---

## File Structure

- `scripts/`: Contains the scripts for PDF downloading, table extraction, and text extraction.
- `data/`: The directory where downloaded PDFs and extracted data will be stored.
- `output/`: Contains the final output (e.g., CSVs or structured dictionaries) after processing the PDFs.

---

## Requirements

- **Python 3.6+**
- **Ghostscript** (for Camelot table extraction)

---

## Conclusion

This project simplifies the process of downloading, extracting, and organizing structured data from government PDFs, allowing for further analysis and reporting. Whether you're working with tables or text, the combination of **Camelot** and **PDFplumber** ensures that both types of data can be efficiently extracted from PDFs.
