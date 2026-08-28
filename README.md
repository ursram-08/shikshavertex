# 🎬 Netflix Content Explorer

## About the Project
This project is an interactive, menu-driven Python application built to analyze the Netflix movies and TV shows catalog. Using Pandas and NumPy, it processes a dataset of over 8,800 titles to perform data cleaning, generate formatted statistical reports, and extract key business insights regarding global production hubs, format dominance, and library distribution.

## Features
The program features a terminal-based interactive menu with the following capabilities:
1. Count of Movies vs. TV Shows
2. Number of titles added each year (Top 10)
3. Top 10 producing countries
4. Top 5 most common genres
5. Rating distribution across the platform
6. Oldest and newest release years
7. Keyword search functionality for titles
8. Filter content added in a specific user-defined year
9. Count of total unique producing countries
10. Summary statistics on release years (Mean, Median, Standard Deviation)

## Tech Stack
* **Python 3.x**
* **Pandas:** Data manipulation, cleaning, and aggregation.
* **NumPy:** Advanced summary statistics.
* **Jupyter Notebook:** Interactive development and execution environment.

## Key Insights Discovered
1. **Format Dominance:** The platform heavily prioritizes feature-length formats over episodic series, maintaining a library where Movies outnumber TV Shows by a significant two-to-one margin.
2. **Global Production Hubs:** Geographic content production is highly centralized; although over 120 unique countries contribute to the database, the United States and India alone account for the vast majority of all available titles.
3. **Library Age Skew:** Summary statistics on release dates demonstrate a strong bias toward highly contemporary media. Half of the entire catalog was released in 2017 or later, despite the platform hosting legacy titles dating as far back as 1925.

## How to Run
1. Clone this repository or download the files to your local machine.
2. Ensure the `netflix_titles.csv` file is in the same directory as the notebook.
3. Open `netflix_analysis.ipynb` in Jupyter Notebook, JupyterLab, or VS Code.
4. Run all cells to launch the interactive terminal menu. 
5. Enter a number between 1 and 11 to explore the data.
