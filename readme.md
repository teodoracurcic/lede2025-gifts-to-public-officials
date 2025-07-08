# Filed, Shelved, Disclosed

This project is part of my work for the [Lede Program](https://ledeprogram.com) at Columbia Journalism School. It investigates patterns and inconsistencies in the official records of gifts received by Serbian public officials between 2015 and 2024.

Public officials in Serbia are legally required to report gifts received during their official duties. These declarations are published by the Anti-Corruption Agency in a public register. This project analyzes the dataset across several dimensions: volume over time, gender patterns, types and values of gifts, retention status, missing information, and outliers.

## Full Analysis and Code

A full breakdown of the extraction, cleaning, and analysis process is documented in [`gifts_analysis.ipynb`](https://github.com/teodoracurcic/lede2025-gifts-to-public-officials/blob/main/gifts_analysis.ipynb).  
All code and the final cleaned dataset are available in the repository.

## Data Source

The data comes from public registers published by the Agency for the Prevention of Corruption of the Republic of Serbia. The data was originally published as 10 separate annual PDFs. These were merged into two combined files — one for 2015–2019 and one for 2020–2024 — because the table structure changed starting in 2020, requiring different extraction logic. Each entry in the dataset includes some or all of the following fields:

- Recipient's name & institution he/she works in  
- Date when the gift was received  
- Description of the gift  
- Gift giver or occasion  
- Estimated value  
- Final status (kept, returned, etc.)

## Tools and Libraries

The project was developed in Python using the following libraries:
- `natural_pdf` – for extracting data from PDF files  
- `pandas` – for data manipulation, merging, and cleaning  
- `numpy` – for handling null values and numeric operations  
- `openpyxl` – for loading `.xlsx` files  
- `transliterate` – for converting Serbian Cyrillic into Latin script  
- `matplotlib` – for visualizations in the context of data analysis  
- `re` – for regular expressions and cleaning inconsistent entries  
- `collections` – for counting how often different gift categories appear in the dataset  

## Data Cleaning and Processing

The raw data was compiled from multiple PDF files, each representing a different year. The processing steps included:

1. **Standardizing Columns:** Renamed and aligned column headers across years  
2. **Merging Datasets:** Concatenated cleaned files into one combined DataFrame  
3. **Cleaning Descriptions:** Normalized inconsistent entries in the "gift" column using regex and manual mapping  
4. **Handling Missing Values:** Identified and flagged entries with missing value or description fields  
5. **Gender Assignment:** Inferred gender from first names using a predefined name-gender mapping for analysis purposes  
6. **Value Conversion:** Transformed reported values to numeric format where applicable  
7. **Gift Categorization:** Created new categorical fields to group gifts (e.g., alcohol, books, plaques, icons)  
8. **Status Normalization:** Simplified gift outcome statuses into key categories: kept, returned, or institutionalized  

## Key Questions Explored in the Jupyter Notebook

- How many gifts are reported each year, and are there patterns in volume over time?  
- Who receives more gifts—men or women—and how do gift types vary by gender?  
- What are the most commonly reported gifts, and how do they differ in value?  
- Are gifts more often kept, returned, or passed on to institutions?  
- How complete and consistent is the dataset overall?  
- What are the most unusual or high-value gifts reported?  

## Output

The final analysis is structured as a visual data story, with each section corresponding to a research question. The project is available at:  
[https://teodoracurcic.github.io/lede2025-gifts-to-public-officials/](https://teodoracurcic.github.io/lede2025-gifts-to-public-officials/)

## Author

Teodora Ćurčić  
Data & investigative journalist  
[Github](http://github.com/teodoracurcic)  
[LinkedIn](https://www.linkedin.com/in/teodora-curcic-27a93884/)