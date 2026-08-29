# 🎬 Netflix Content Explorer

![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=flat&logo=pandas)
![NumPy](https://img.shields.io/badge/NumPy-Statistics-013243?style=flat&logo=numpy)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=flat&logo=jupyter)

## 📌 Project Overview
The **Netflix Content Explorer** is an interactive, menu-driven Python application designed to analyze the global Netflix movies and TV shows catalog. Built for the command line, it processes a comprehensive dataset to perform robust data cleaning, generate custom formatted ASCII tables, and extract actionable business insights regarding content trends, geographic production hubs, and library distribution.

## 🗄️ Dataset Information
* **Name:** Netflix Titles Dataset
* **Source:** Kaggle
* **File:** `netflix_titles.csv`
* **Size:** ~8,800 rows, 12 columns
* **Attributes:** `show_id`, `type`, `title`, `director`, `cast`, `country`, `date_added`, `release_year`, `rating`, `duration`, `listed_in` (genres), `description`

## 🛠️ Technical Implementation Details

### Data Cleaning & Feature Engineering Pipeline
Before the user can query the dataset, the `load_and_clean_data()` function automatically sanitizes the data using Pandas:
* **Null Value Imputation:** Fills missing `country`, `director`, `cast`, and `rating` values with context-appropriate defaults (e.g., "Unknown", "Not Listed").
* **Datetime Parsing:** Strips leading/trailing whitespace from `date_added`, dynamically converts it to a standard Pandas datetime format, and extracts a new `year_added` integer column for temporal analysis.
* **Regex Data Extraction:** Uses regular expressions (`r'(\d+)'`) to parse the `duration` text column, separating movie runtimes (minutes) from TV show formats (seasons) into a computable `duration_num` float column.
* **Data Flattening:** Utilizes Pandas `.str.split()` and `.explode()` to accurately count attributes where a single title has multiple genres, directors, or producing countries.

### Error Handling & UI
* **Graceful Exceptions:** Utilizes `try-except` blocks to catch `FileNotFoundError` upon initialization and `ValueError` when users input non-numeric types during year-based search prompts.
* **Dynamic Terminal Clearing:** Implements an OS-agnostic screen clearing function (`os.system('cls' or 'clear')`) to ensure the console remains clean and readable after every query.
* **Custom Table Generator:** Features a reusable `print_formatted_table()` helper function utilizing Python f-strings to align console outputs into clean, readable ASCII tables.

## ⚙️ Interactive Analytics Menu
The program provides a 14-option interactive terminal UI grouped into core requirements and advanced analytics:

**Core Content Analytics**
1. Count of Movies vs. TV Shows
2. Number of titles added each year (Top 10 recent years)
3. Top 10 producing countries (Handling multi-country collaborations)
4. Top 5 most common genres (Handling multi-genre titles)
5. Rating distribution across the platform
6. Oldest and newest release years
7. Keyword search functionality for specific titles (Case-insensitive)
8. Filter content added in a specific user-defined year
9. Count of total unique producing countries (Excluding unknowns)
10. Summary statistics on release years (Mean, Median, Standard Deviation, Q1, Q3 using NumPy)

**Advanced Exploration Tools**
11. Top 5 Directors with the most content (Excluding missing data)
12. Top 5 Longest Movies (Utilizing the engineered minute-duration column)
13. Advanced Multi-Filter Search (Genre text-match + exact Year Added)
14. Clean terminal exit
