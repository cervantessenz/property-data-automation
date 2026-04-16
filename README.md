# Property Data Automation

Automation scripts for property data processing, including utility provider lookup, address matching, and sewer provider extraction.

---

## 📌 Overview

This repository contains a set of Python scripts designed to automate the enrichment of property data. It replaces manual workflows by programmatically identifying utility providers and linking property records using geocoding, GIS services, fuzzy matching, and web scraping.

---

## ⚙️ Modules

### 🔌 Utility Provider Lookup
Scripts that determine utility providers based on property addresses:

- **water_provider_lookup**  
  Retrieves water providers using ArcGIS and Portland Maps GIS services  

- **garbage_provider_lookup**  
  Identifies garbage haulers using GIS boundary data with coordinate projection (Web Mercator)  

- **electric_provider_lookup**  
  Queries ArcGIS electric service territory data  

- **gas_provider_lookup**  
  Queries ArcGIS natural gas service territory data  

---

### 🧠 Address Matching
- **fuzzy_matching_pids**  
  Matches property addresses to internal property IDs  
  - Uses normalization (abbreviations, directions)  
  - Performs exact matching first  
  - Applies fuzzy matching (RapidFuzz) for unmatched records  
  - Optimized with multiprocessing  

---

### 🌐 Sewer Provider Extraction
- **sewer_scraper**  
  Automates browser interaction with PortlandMaps.com using Selenium  
  - Searches by property ID  
  - Navigates to utilities section  
  - Extracts sewer provider information  
  - Handles dynamic page loading and missing data  

---

## 🧰 Technologies Used

- Python  
- Pandas  
- Requests  
- RapidFuzz (fuzzy matching)  
- Selenium (web automation)  
- ArcGIS REST APIs  

---

## 📂 Repository Structure
electric_provider_lookup
gas_provider_lookup
water_provider_lookup
garbage_provider_lookup
fuzzy_matching_pids
sewer_scraper

---

## 📥 Input Data

Scripts require CSV files containing property address data.

Example format:
full_address
123 Main St Portland OR
456 Oak Ave Beaverton OR

--

⚠️ **Note:**  
Actual property datasets are not included in this repository for privacy and security reasons.

---

## 🔄 Workflow (Typical Usage)

1. Prepare address dataset  
2. Run utility lookup scripts (water, garbage, electric, gas)  
3. Match addresses to property IDs using fuzzy matching  
4. Run sewer scraper using property IDs  
5. Export enriched dataset with all utility providers  

---

## 🚀 Purpose

- Eliminate manual utility provider lookup  
- Improve data consistency across property records  
- Reduce operational friction in property management workflows  
- Enable scalable data enrichment processes  

---

## 📈 Real-World Use

- Used to populate utility provider data across multiple properties  
- Integrated into operational workflows and automation systems  
- Reduced manual lookup effort and improved processing speed  
- Increased accuracy in property management records  

---

## 🔧 Future Improvements

- Combine all scripts into a single unified pipeline  
- Add logging and error handling  
- Support batch processing and CLI execution  
- Expand to additional data sources and utilities  
