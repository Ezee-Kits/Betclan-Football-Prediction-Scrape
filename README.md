# 🏆 Betclan Football Prediction Scraper

## 📘 Overview
**Betclan Football Prediction Scraper** is an automated Python script developed by **Ezee Kits** that scrapes daily or tomorrow's football predictions from [Betclan.com](https://www.betclan.com).  
It collects team statistics, probabilities (1X2, Over/Under 2.5, Both Teams To Score), and match timing, organizes them into a structured dataset, and saves the results as a `.csv` file for data analysis or football prediction projects.

---

## ⚙️ Features
- Scrapes **Betclan football predictions** automatically.  
- Extracts **home win**, **draw**, and **away win percentages**.  
- Collects **Over/Under 2.5** and **Both Teams To Score** stats.  
- Supports both **today’s** and **tomorrow’s** match predictions.  
- Automatically **removes duplicate entries** for clean data.  
- Saves results in an easily accessible **CSV format**.  
- Uses custom helper functions from a local `func.py` module for modular design.

---

## 🧠 How It Works
1. Checks the current date using `match_day_date` to determine if predictions should be scraped for today or tomorrow.  
2. Sends a request to the appropriate Betclan prediction URL using `requests`.  
3. Parses HTML with **BeautifulSoup** to extract match links and team prediction stats.  
4. Loops through each prediction page to gather:
   - Match Date and Time  
   - Home and Away Team names  
   - Home Win / Draw / Away Win Percentages  
   - Over 2.5 and Under 2.5 Predictions  
   - Both Teams To Score (BTS) and One Team To Score (OTS) data  
5. Stores all extracted information in a Python dictionary.  
6. Saves data using the custom `saving_files()` function.  
7. Cleans duplicates using `drop_duplicate()` for reliable output.

---

## 🧩 Tech Stack
- **Python 3.x**
- **BeautifulSoup4** — for HTML parsing  
- **Requests** — for fetching Betclan web pages  
- **LXML** — (if used in func module for structured parsing)
- **Custom Python Utilities (`func.py`)** — includes:
  - `requests_init()`
  - `saving_files()`
  - `drop_duplicate()`
  - `sorting_values()`
  - `save_daily_csv()`
  - `match_day_date()`

---

## 🧰 Setup Instructions
Follow these steps to set up and run the project on your system:

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/betclan-football-scraper.git
cd betclan-football-scraper
```

### 2. Install Dependencies
```bash
pip install requests beautifulsoup4 lxml
```

### 3. Ensure You Have the `func.py` File
Make sure the helper functions file (`func.py`) is in the same directory as this script.  
It should include functions like `requests_init`, `saving_files`, `drop_duplicate`, etc.

### 4. Run the Script
```bash
python betclan_scraper.py
```

---

## 💻 Usage Example
```python
from betclan_scraper import betclan_func

# Run scraper to fetch today's predictions
betclan_func()
```

After running, a CSV file will be created automatically in the **daily directory** returned by `save_daily_csv()` (e.g., `/2025-10-19/betclan.csv`).

---

## 📂 Example Output (betclan.csv)
| DATE | TIME | HOME TEAM | AWAY TEAM | HOME PER | DRAW PER | AWAY PER | UNDER 2.5 | OVER 2.5 | BTS | OTS | NAME |
|------|------|------------|------------|-----------|-----------|-----------|-------------|-------------|------|------|------|
| 19.10.2025 | 16:00 | Arsenal | Chelsea | 54 | 26 | 20 | 45 | 55 | 60 | 40 | BCL |
| 19.10.2025 | 18:30 | Napoli | Roma | 48 | 29 | 23 | 41 | 59 | 63 | 37 | BCL |

---

## 🎯 Example Use Case
- **Data Analysis**: Combine Betclan data with other prediction sources (like Forebet, Statarea, Accagenerator) for **machine learning** or **Kelly Criterion** betting models.  
- **Automation**: Integrate it into a daily automated script to fetch fresh football predictions.  
- **Research**: Analyze team performance prediction patterns and success rates.  

---

## 👨‍💻 Author
**Ezee Kits**  
- GitHub: [@Ezee-Kits](https://github.com/Ezee-Kits)  
- YouTube: [Ezee Kits](https://www.youtube.com/@Ezee_Kits)

---

## 📜 License
This project is licensed under the **MIT License**.  
You are free to use, modify, and distribute it with proper credit to the author.

---

## 🚀 Future Improvements
- Add **multi-threading** for faster scraping.  
- Implement **logging** and error handling for stability.  
- Integrate **database storage** (SQLite or MongoDB).  
- Expand support for other prediction platforms.  
