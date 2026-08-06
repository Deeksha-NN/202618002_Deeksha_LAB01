 Books Dataset Exploratory Data Analysis

This repository contains a Python-based exploratory data analysis (EDA) of a books dataset, presumably scraped from `books.toscrape.com`. The analysis covers data cleaning, feature engineering, and the generation of multiple visualizations to extract insights into book pricing, ratings, stock availability, and categorical trends.

## Project Overview

The primary objective of this project is to perform a comprehensive EDA on a raw dataset of 100 books. The workflow is divided into three main tasks:

1.  **Initial Assessment:** Loading the data and checking for missing values, total records, and duplicates.
2.  **Data Preprocessing:** Cleaning text fields, formatting numeric columns (like price and stock), and engineering new features (like word counts and fiction vs. non-fiction flags).
3.  **Visualization and Analysis:** Using `matplotlib` and `seaborn` to uncover statistical patterns and relationships within the cleaned data.

## Features & Analysis

The Jupyter Notebook (`202618002_deeksha_lab01.ipynb`) performs the following operations:

### 1. Data Cleaning
*   **Whitespace Removal:** Cleans up extra spaces in text-heavy columns (`title`, `category`, `availability`, `description`).
*   **Data Type Conversion:** 
    *   Strips currency symbols and converts the `price` column to `float`.
    *   Converts the `rating` column to a numeric format.
*   **Regex Extraction:** Extracts the integer stock count from the verbose `availability` string.

### 2. Feature Engineering
*   **`description_word_count`:** Calculates the length of each book's description.
*   **`price_band`:** Categorizes books into 'Low', 'Medium', or 'High' price tiers using quantiles.
*   **`is_fiction`:** A boolean flag determining if a book belongs to a predefined list of fiction categories.

### 3. Visualizations
The script generates a comprehensive dashboard (`books_analysis.png`) containing four key plots:
*   **Price Distribution:** A histogram showing the frequency of different price points.
*   **Rating Distribution:** A count plot displaying the balance of 1 to 5-star ratings.
*   **Average Price by Category:** A bar chart highlighting the most expensive genres.
*   **Average Rating by Category:** A bar chart showing which genres are best received by readers.

Additionally, it generates a **Word Cloud** (`description_wordcloud.png`) derived from the combined text of all book descriptions.

## Dependencies

To run the notebook, ensure you have the following Python libraries installed:

*   `numpy`
*   `pandas`
*   `matplotlib`
*   `seaborn`
*   `wordcloud`

## Usage

1.  Clone this repository.
2.  Ensure your raw dataset (`books.csv`) is placed in the correct directory (or update the file path in the notebook).
3.  Run the Jupyter Notebook cells sequentially. 
4.  The script will output a clean dataset named `books_cleaned.csv` and save two image files (`books_analysis.png` and `description_wordcloud.png`) to your working directory.

## Data Source Limitations
*Note: As this dataset is sourced from a web scraping sandbox, the data is highly synthetic (e.g., highly uniform stock counts and perfectly balanced rating distributions) and does not represent a real-world retail environment.*
