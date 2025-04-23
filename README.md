# 🕵️‍♂️ company-director-extract--nlp

**Web scraping + NLP tool** to extract director names from company websites using **spaCy**. Automates the process of identifying board members from publicly available corporate web pages, with smart retry handling via **Selenium**, and robust fallback options for improved accuracy and reliability.

---

## 📦 What It Does

This tool automates the end-to-end process of:

- Scraping a list of companies from the **Colombo Stock Exchange (CSE)**
- Searching for each company’s **Board of Directors** page using **ZenRows API + Google Search**
- Extracting director names using **spaCy NLP**
- Handling failed pages by retrying with **Selenium WebDriver**
- Storing successful and failed records in CSVs

---

## 🚀 Features

✅ Extracts board member names using Named Entity Recognition (NER)  
✅ Supports retry fallback for JavaScript-heavy pages  
✅ PDF/WSJ filtering for cleaner data  
✅ Outputs to CSV files for easy analysis  
✅ Fully modular and customizable pipeline  

---

## 🧠 Technologies Used

- `spaCy` (`en_core_web_lg`) for NLP-based name recognition
- `BeautifulSoup`, `requests` for static scraping
- `ZenRows API` for bypassing search & scraping restrictions
- `Selenium` as a fallback for dynamic content
- `pandas` for data management
- `Chrome WebDriver` (headless mode)

---

## 🔄 Pipeline Overview

### Step 1: Scrape CSE Company List

Fetches company names, codes, and market capitalization data from the Colombo Stock Exchange website.

> Output: `top_cse_companies.csv`

### Step 2: Search for Board URLs

Uses Google search via **ZenRows API** with queries like:

"{Company Name} Board of Directors"


Filters out irrelevant or PDF results.

> Outputs: `web_links.csv`, `pdf_links.csv`, `wsj.csv`

### Step 3: NLP-Based Name Extraction

- Extracts visible text from each web page
- Uses **spaCy** to detect `PERSON` entities near board-related keywords
- Cleans and deduplicates names with custom filters

> Output: `directors_names.csv`

### Step 4: Retry Failed URLs with Selenium

For any URLs that failed the initial extraction, uses Selenium WebDriver (headless Chrome) to re-fetch and re-process them.

> Updates: `df_failed.csv`, `df_success.csv`

---

## 🛠️ Requirements

- Python 3.8+
- ChromeDriver installed and available in PATH
- ZenRows API Key

### Install Dependencies

```bash
python -m spacy download en_core_web_lg

