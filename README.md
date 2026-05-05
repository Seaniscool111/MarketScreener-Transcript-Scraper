# MarketScreener Transcript Scraper

## Description
This project is a high-performance Python-based web scraper and automation tool designed to collect financial transcripts (earnings calls, investor conferences, etc.) from MarketScreener. It automates the process of navigating through multiple companies, identifying transcript links, and extracting the full text.

The script goes beyond simple scraping by performing "intelligent parsing." It identifies speaker names and job titles, applying professional formatting (bolding names, italicizing titles) before generating a final polished PDF document. This tool is ideal for financial analysts, researchers, or investors who need to archive and read transcripts offline without the tedious manual "copy-paste" process.

## Features
- **Multi-Company Support:** Scrape transcripts for an unlimited list of companies in one run.
- **Paywall Bypass:** Uses a manual session trigger to allow users to log in with their own credentials before the scraping begins.
- **Intelligent Formatting:** 
    - Detects speaker blocks automatically.
    - Bolds speaker names.
    - Small, italicized font for job titles (e.g., *CFO*, *VP of Engineering*).
- **Automated PDF Generation:** Converts formatted Word documents directly to PDF and cleans up temporary files automatically.
- **Organized Storage:** Automatically creates separate folders for each company (e.g., `/webscrape/CISCO/`, `/webscrape/VEEVA/`).

## Technologies Used
- **Python**
- **Selenium:** For browser automation and dynamic content loading.
- **BeautifulSoup4:** For advanced HTML parsing and speaker detection.
- **python-docx:** To programmatically build and style documents.
- **docx2pdf:** For professional-grade PDF conversion.
- **Webdriver Manager:** To handle automatic Chrome driver updates.

## Installation
Ensure you have **Google Chrome** and **Microsoft Word** installed (Word is required by the `docx2pdf` library for the conversion process).

1. Clone this repository or download the script.
2. Install the required libraries:
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
5. The script will automatically scroll to the bottom of the history, extract all links, and begin the download/conversion process.

## Disclaimer
This tool is intended for personal research and archival purposes. Always respect the Terms of Service of the website being scraped.
