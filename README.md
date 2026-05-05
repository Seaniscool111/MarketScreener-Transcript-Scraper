# Financial Transcript Automation Pipeline

## Description
This project is a high-performance automation pipeline built with Python and Selenium to extract, format, and archive financial transcripts from MarketScreener. It handles the full lifecycle of data collection, from bypassing paywalls via authenticated sessions to generating professionally formatted PDFs.

This version introduces a high-performance, two-phase process: first, it rapidly scrapes and saves all transcripts as formatted `.docx` files. Second, it performs a single batch operation to convert all documents to PDF, dramatically reducing processing time and system overhead.

## Key Features
- **Dynamic List Discovery:** Implements an infinite scroll loop to capture years of historical transcript data, not just what's initially visible.
- **Paywall-Aware Session:** Uses a manual trigger to allow users to log in securely before the automation takes over.
- **Intelligent Formatting:** 
    - Automatically identifies "Speech Blocks" via CSS class analysis (`.txt-bold`, `speech-xxxxx`).
    - Applies bold styling to speaker names and italicized, condensed font for executive titles.
- **High-Performance Batch Conversion:** Separates scraping from conversion. All transcripts for a company are saved as DOCX first, then converted to PDF in a single, fast batch operation.
- **Automated Cleanup:** Automatically deletes the temporary `.docx` files after the PDF conversion is complete, leaving a clean output directory.

## Workflow
The script follows a robust, multi-stage process for each company:

`[Navigate & Login]` **->** `[Scroll to Load All Links]` **->** `[Loop & Save All as DOCX]` **->** `[Batch Convert to PDF]` **->** `[Cleanup DOCX Files]`

## Technologies Used
- **Python**
- **Selenium & Webdriver Manager:** For dynamic browser automation and scroll handling.
- **BeautifulSoup4:** For advanced HTML parsing and speaker identification.
- **python-docx:** For programmatic document construction and typography.
- **docx2pdf:** Used for its efficient batch-folder conversion capabilities.

## Installation
*Note: This script requires **Microsoft Word** to be installed on the host machine for PDF conversion.*

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/Financial-Transcript-Automator.git
   ```
2. Install dependencies:
   ```bash
   pip install selenium webdriver-manager beautifulsoup4 python-docx docx2pdf
   ```

## Usage
1. Open the script and update the `COMPANIES` list with your target MarketScreener URLs.
2. Run the script from your terminal:
   ```bash
   python extract_transcript.py
   ```
3. A Chrome window will open. Log in to your account and accept any cookie banners.
4. Once you are logged in, return to your terminal and type `READY` to start the automation.
5. The script will handle the rest, creating subfolders for each company in the `webscrape` directory filled with the final PDF transcripts.

## Disclaimer
This project is for educational and personal research purposes only. Users are responsible for ensuring their use of the tool complies with the target website's Terms of Service.
