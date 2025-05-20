# PDF Combiner

## Description

PDF Combiner is a Python utility that combines multiple PDF files into a single document, with automatic splitting when the file size approaches a specified limit. This tool is perfect for compiling collections of PDFs while ensuring the output files remain manageable in size.

## Key Features

- **Multi-PDF Merging**: Combines multiple PDF files into a consolidated document.
- **Automatic Size Splitting**: Splits output into multiple files if size exceeds the specified limit.
- **Recursive Directory Scanning**: Finds all PDFs in a directory and its subdirectories.
- **Progress Visualization**: Shows real-time progress with estimated time remaining.
- **Size Estimation**: Provides estimates of final file sizes and required number of output files.
- **Error Handling**: Continues processing even if individual PDFs have issues.

## Use Cases

- Combining PDFs downloaded by the Single Domain PDF Scraper
- Consolidating related documents into a single file
- Preparing PDFs for upload to systems with file size limits
- Creating document archives with manageable file sizes

## Requirements

- Python 3.x
- PyPDF2 library
- tqdm library (for progress bars)

## Installation

```bash
pip install PyPDF2 tqdm
```

## Usage

1. Run the script from the command line:
   ```
   python PDF_Combiner.py
   ```

2. Enter the directory containing PDF files to combine.

3. Provide a base name for the output files (combined PDFs will be named `basename_1.pdf`, `basename_2.pdf`, etc.).

4. Specify the maximum file size in MB (default is 10MB).

5. The script will:
   - Search for PDF files in the specified directory and subdirectories
   - Count the total number of pages to process
   - Estimate the combined size and number of output files
   - Process and combine the PDFs with real-time progress indicators
   - Save the output to the current working directory

## How It Works

1. The script recursively finds all PDF files in the specified directory.

2. It estimates the total combined size to determine approximately how many output files will be needed.

3. It processes each PDF file, adding pages to the current output document.

4. When the size of the current document approaches the specified limit, it saves the file and starts a new one.

5. The process continues until all PDFs have been processed.

## Notes

- PDF order is determined by filename (alphabetical sorting).
- The script calculates file sizes dynamically during processing to ensure accurate splitting.
- For very large collections of PDFs, the process may take some time, but the progress bar provides clear feedback.
- If a PDF is corrupted or cannot be read, the script will skip it and continue with the remaining files.

## Workflow Integration

This script is designed to work perfectly with the Single Domain PDF Scraper:

1. Use the Single Domain PDF Scraper to download PDFs from a website
2. Use the PDF Combiner to consolidate the downloaded PDFs into manageable files
3. Upload the combined PDFs to your preferred system (e.g., custom GPTs, AI tools, document management systems)
