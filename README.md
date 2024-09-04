# Netflix-Analysis

Overview

This Python script was created to clean, transform, and prepare Netflix data for analysis in Tableau. The primary focus was addressing the issues in the country column, where some shows listed multiple countries in a single cell. This made it difficult to perform accurate country-based analysis in Tableau. The script outputs two CSV files:

A cleaned version of the Netflix dataset with necessary transformations.
A mapping file that links each unique country to the relevant show_id for improved country-level analysis.
Process

Initial Cleaning:
In the first phase of cleaning, the following steps were taken:

Removed empty rows and duplicates.
Trimmed whitespace from all column values to standardize the data for further analysis.
Challenge in Tableau:
When attempting to analyze the dataset in Tableau, it became clear that the country column was not suitable for direct use. In the dataset, multiple countries were often listed together (e.g., "United States, India") for a single show, which led to inaccurate filtering when searching by individual countries. For example, searching for "United States" content only returned shows exclusively tied to the US, excluding those shared with other countries.

Solution:
To resolve this issue, instead of modifying the Tableau queries, the data cleaning script was enhanced using Python, Pandas, and PandasQL to output two separate CSV files:

Cleaned Netflix Data:
The cleaned dataset with consistent country data and standard transformations applied.
Each country is now treated consistently across the dataset.
Country to Show ID Mapper:
A separate mapping file that breaks down each country and links it to relevant show_ids, ensuring that filtering by country in Tableau would return all relevant results.
By using this mapping file and linking it to the main dataset in Tableau, the accuracy of the analysis improved significantly. For instance, a search for "Argentina" content initially returned only 35 shows. After implementing this improved process, the search revealed that 65 shows were actually available in Argentina.

Further Improvements:
This script represents the second iteration of the data cleaning process, and there are further opportunities to enhance the workflow for even better results in Tableau.

Files

netflix_titles.csv: The original raw dataset from Kaggle.
netflix_titles_cleaned.csv: The cleaned dataset generated using the script.
CountryToShowidMapper.csv: A mapping file linking each country to its respective show_id for accurate country-level filtering in Tableau.
Usage

Run the Python script to clean the raw netflix_titles.csv and generate the cleaned data files.
Use netflix_titles_cleaned.csv as the primary dataset for analysis in Tableau.
Use CountryToShowidMapper.csv to map countries to their respective shows, ensuring more accurate filtering by country in Tableau.
Link both datasets in Tableau for enhanced country-based insights.
