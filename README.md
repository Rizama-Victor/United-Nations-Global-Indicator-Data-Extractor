# 🌍 United Nations Global Indicator Data Extractor
This repository contains the implementation of my project titled _"United Nations Global Indicator Data Extractor"_, at the National Centre for Artificial Intelligence and Robotics (NCAIR), Nigeria.

---
## 🚀 Project Overview

The goal of this project was to scrape data from the United Nations (UN) Database - Global Indicators to gather comprehensive global indicator data for every country in the world, as well as various regions. The project focused on four key indicators:
- Economic Indicators
- Environmental and Infrastructural Indicators
- General Information
- Social Indicators

---

## 🧰 Tools and Technologies Used 

| **Tool / Library**                  | **Purpose in Project**                                                                 |
|------------------------------------|-----------------------------------------------------------------------------------------|
| **pandas**                          | Used to structure, clean, and manage the extracted UN indicator data efficiently.  |
| **requests**                        | Helped fetch web content and download HTML pages from the UN data source.         |
| **BeautifulSoup (bs4)**             | Parsed and extracted specific indicator values and metadata from HTML pages.  |
| **re (Regular Expressions)**        | Used to clean text patterns and match specific indicator entries within web data.  |
| **os**                              | Managed file paths and handle directory operations during data export.      |
| **tkinter**                         | Was used to build the graphical user interface (GUI) for selecting indicators.         |
| **tkinter.ttk**                     | Helped enhance the GUI with improved widgets such as dropdowns and labels.        |

---

## 🔁 Step-by-Step Procedure (Class responsibilities)

The application was organized into four main classes. Each class encapsulated a specific responsibility in the extraction pipeline:

### 1. Gui  
- **Purpose:** Handled all user interactions and controls.  
- **What it did:**  
  - Built and displayed the tkinter window and widgets.  
  - Triggered the extraction workflow when the user pressed the extract buttons.  
  - Displayed success|error dialogs and progress feedback to the user.

### 2.WebsiteAccess
- **Purpose:** Managed network access and HTTP communication with the UN data pages.  
- **What it did:**  
  - Constructed the target URL(s) for a selected indicator.  
  - Performed HTTP requests (GET) to download the HTML content of indicator pages.  
  - Handled basic request validation and retried or reported failures when needed.  
  - Returned raw HTML for downstream parsing.

### 3. WebsiteScraping  
- **Purpose:** Parsed downloaded HTML and located the raw indicator tables/sections.  
- **What it did:**  
  - Used an HTML parser (BeautifulSoup) to find the element(s) containing indicator data (tables, divs).  
  - Extracted raw text fragments, table rows, and relevant fields (country, year, value).  
  - Returned the scraped, but not-yet-cleaned, rows to the extraction layer.

### 4. WebsiteDataExtraction  
- **Purpose:** Cleaned, structured, and partitioned the scraped indicator data.  
- **What it did:**  
  - Normalized and cleaned scraped strings (removed extra whitespace, fixed numeric formatting) using regex and parsing rules.  
  - Converted scraped rows into a `pandas.DataFrame` with proper columns (country, year, value, indicator).  
  - Performed missing-value handling and basic validation checks.  
  - Saved final output files (CSV | Excel) into organized folders and returned the output path to the GUI.


---

## Results

The Results of the extraction process can be acessed [**here**](Results.zip).

---
## ⚠️ Disclaimer

This README file is a summary of the project’s implementation. You can access the full program script [**here**](United-Nations-Global-Indicator-Data-Extractor.ipynb). Kindly also note that the script was developed based on the structure and functionality of the [**source website**](https://data.un.org/default.aspx) at the time of creation. If the website changes in the future, the script may require minor updates to remain fully functional.

---

