# company-director-extract--nlp
Web scraping tool to extract director names from company websites using spaCy NLP. Automates the process of identifying board members from publicly available information, with error handling and retry mechanisms for improved accuracy and reliability.

# 🕵️‍♂️ Company Director Extractor

This project is a **web scraping and natural language processing (NLP)** tool designed to automatically extract the names of company board members and directors from corporate websites. It uses **BeautifulSoup**, **requests**, and **spaCy's powerful `en_core_web_lg` model** to identify and extract named entities labeled as `PERSON`, with a fallback mechanism for handling failed extractions.

---

## 🚀 Features

- Extracts visible text from company websites
- Uses spaCy's NLP to detect names labeled as `PERSON`
- Cleans and filters out irrelevant or malformed names
- Automatically retries failed URLs
- Saves results into separate `success` and `failed` CSV files
- Easily customizable to support more advanced scraping and NLP logic

---


