# Simple Bunkr Downloader

A Python-based Bunkr downloader that utilizes Playwright for browser automation to fetch and download images and videos from specified URLs. This tool supports downloading from both Bunkr albums and individual file URLs, while also logging any issues encountered during the download process.

## Features

- Download pictures and videos from specified URLs.
- Handles both single file and album downloads.
- Logs URLs that encounter errors for troubleshooting.
- Progress indication during downloads.

## Dependencies

- Python 3
- `playwright` - for browser automation and downloading content.
- `BeautifulSoup` (bs4) - for HTML parsing
- `requests` - for HTTP requests
- `rich` - for progress display in the terminal.

## Directory Structure

```
project-root/
├── helpers/
│ └── playwright_downloader.py  # Python script to download single media from a Bunkr URL using Playwright
├── downloader.py               # Python script to download from a Bunkr URL
├── main.py                     # Main Python script to run the downloader
├── URLs.txt                    # Text file containing album URLs
└── session_log.txt             # File for temporary data storage
```

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Lysagxra/SimpleBunkrDownloader.git

2. Navigate to the project directory:
   ```bash
   cd SimpleBunkrDownloader

3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt

4. Ensure you have Playwright installed and set up installing Firefox:
   ```bash
   playwright install firefox

## Single Media Download

To download a single media from an URL, you can use `downloader.py`, running the script with a valid album or media URL.

### Usage
```bash
python3 downloader.py <bunkr_media_url>
```

### Example
```
python3 downloader.py https://bunkr.si/a/PUK068QE
```

## Batch Download

To batch download media from multiple URLs, you can use the `main.py` script. This script reads URLs from a file named `URLs.txt` and downloads each one using the media downloader.

### Usage

1. Create a file named `URLs.txt` in the root of your project, listing each URL on a new line.

2. Run the batch download script:
```
python3 main.py
```
3. The downloaded files will be saved in the `Downloads` directory.

## Logging

The application logs any issues encountered during the download process in a file named `session_log.txt`. Check this file for any URLs that may have been blocked or had errors.
