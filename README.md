🏈 NFL Injury Report Scraper🌟 Project 
Overview
This Python script is designed to automatically scrape the official NFL team websites for weekly injury report data, clean and standardize the structure, and consolidate all findings into a single, clean CSV file. 
It leverages Selenium to handle the dynamically loaded content found on the official NFL team sites.
Key Features
32-Team Coverage: 
Loops through all NFL teams using pre-defined URL and abbreviation lists.
Dynamic Loading: 
Uses Selenium and explicit waits (WebDriverWait) to handle tables loaded via JavaScript.Data 
Consolidation: Combines all team-week reports into a single, comprehensive DataFrame (all_team_inj_report.csv).
Metadata Tagging: Automatically adds columns for season, game_type, team, and week to each row for easy analysis.🚀 

Getting Started
Follow these steps to get a local copy of the project up and running.

Prerequisites
You need Python installed (Python 3.8+ recommended) and a modern web browser (e.g., Chrome, Edge) for Selenium to use.

Installation
Clone the Repository:Bashgit clone [YOUR-REPO-URL]
cd [YOUR-REPO-NAME]
Install Dependencies:
This project requires the following libraries. 
It's recommended to install them in a virtual environment.
Bashpip install pandas selenium beautifulsoup4
WebDriver Setup (Automated):
This script uses Selenium Manager (available in modern Selenium versions), which should automatically detect your installed Chrome or Edge browser and download the correct driver. 
No manual download of chromedriver.exe is required.💡

Usage
The primary entry point for execution is the run_team_injury_reports() function.ConfigurationBefore running, ensure the following variables are correctly defined in your main script, or passed as arguments:
Variable
TypeExample
Description
nfl_team_urlslist[...]
The list of 32 official team home page URLs.nfl_team_abbreviationslist[...]
The 32 team abbreviations ('BUF', 'MIA', etc.).
week_numberint18
The final regular season week to scrape (e.g., 18).seasonstr'2024'The year for which data is being scraped.
Running the ScraperExecute the main function:Python# In your main Python script (e.g., main.py)
run_team_injury_reports()
OutputThe final consolidated report will need to be customized
📂 Project Structure (Simplified)/
├── README.md               # This file
├── injury_scraper.py       # Contains get_team_injury_report() and run_team_injury_reports()
├── requirements.txt        # List of Python dependencies
└── data/                   # (Optional: Directory where results are stored)
    └── 2025/
        └── Teams/
            └── ... (individual team files, if saved)
⚠️ Known LimitationsCustom Websites: Teams that use custom web platforms (e.g., the Dallas Cowboys and Green Bay Packers) may cause the get_team_injury_report() function to fail with a NoSuchElementException because the table selector (TABLE_XPATH) is specific to the standardized NFL platform. These teams will require unique XPaths to be handled separately.Scraping Ethics: Be mindful of the load you place on the team servers. The script includes a time.sleep() within the scraping logic to prevent excessive requests.
