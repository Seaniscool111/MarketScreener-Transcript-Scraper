# Financial Transcript Automation Pipeline

## Description
This project is a high-performance automation pipeline built with Python and Selenium to extract, format, and archive financial transcripts from MarketScreener. It handles the full lifecycle of data collection: from bypassing paywalls via authenticated sessions to generating professionally formatted PDFs.

This version features a **High-Performance Batch Conversion** engine. The script rapidly scrapes and styles all transcripts as `.docx` files first, then performs a single batch operation to convert the entire folder to PDF, significantly reducing processing time and Microsoft Word overhead.

## Key Features
- **Dynamic List Discovery:** Implements an infinite scroll loop to capture years of historical transcript data, overcoming "lazy-loading" web designs.
- **Paywall-Aware Session:** Uses a manual trigger to allow users to log in securely before the automation takes over.
- **Semantic Parsing & Formatting:** 
    - Automatically identifies "Speech Blocks" via CSS class analysis.
    - Applies bold styling to speaker names and italicized, condensed font for executive titles.
- **Batch PDF Pipeline:** Optimized conversion process that handles entire directories at once.
- **Automated Cleanup:** Automatically purges temporary files to maintain a clean, PDF-only final archive.

## Workflow
`[Navigate & Login]` **->** `[Scroll to Load History]` **->** `[Scrape & Style All as DOCX]` **->** `[Batch Convert to PDF]` **->** `[Cleanup]`

## Technologies Used
- **Python** (Selenium, BeautifulSoup4, python-docx, docx2pdf)
- **Webdriver Manager:** For automatic Chrome driver synchronization.
- **Microsoft Word Interop:** Used for professional-grade PDF rendering.

## Installation
*Note: This script requires **Microsoft Word** and **Google Chrome** to be installed.*

1. Clone the repository and install dependencies:
```bash
pip install selenium webdriver-manager beautifulsoup4 python-docx docx2pdf
```

## Instructions
1. Open `extract_transcript.py` and add your target MarketScreener URLs to the `COMPANIES` list.
2. Run the script:
   ```bash
   python extract_transcript.py
   ```
3. A Chrome window will open. Log in to your account and accept any cookie banners.
4. Once you are on the transcript list page, return to your terminal and type `READY`.
5. The script will automatically scroll to the bottom of the history, extract all links, and begin the high-speed download and batch conversion process.

## Disclaimer
This tool is intended for personal research and archival purposes. Always respect the Terms of Service of the website being scraped.
