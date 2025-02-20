# Web Scraping with Selenium and PostgreSQL

## Overview
This project demonstrates how to use Python with Selenium to scrape data from a website, process it using pandas, and store the results in a PostgreSQL database.

## Technologies Used
- **Python**
- **Selenium** for web scraping
- **pandas** for data manipulation
- **BeautifulSoup** for HTML parsing
- **SQLAlchemy** for database interaction
- **PostgreSQL** for storing the scraped data

## Setup Instructions

### Prerequisites
Ensure you have the following installed:
- Python (3.8 or higher)
- Google Chrome browser
- ChromeDriver (compatible with your Chrome version)
- PostgreSQL

### Install Dependencies
```bash
pip install selenium pandas beautifulsoup4 sqlalchemy psycopg2-binary
```

### Configure PostgreSQL
Update the `create_engine` line in the script with your PostgreSQL credentials:
```python
engine = create_engine('postgresql://postgres:*Your_Database_Password*@localhost:5432/DIY')
```
Replace `*Your_Database_Password*` with your actual database password.

## Code Explanation

### Selenium WebDriver Setup
The script configures Chrome options for a smoother browsing experience:
```python
option = Options()
option.add_argument("--disable-infobars")
option.add_argument("start-maximized")
option.add_argument("--disable-extensions")
option.add_experimental_option(
    "prefs", {"profile.default_content_setting_values.notifications": 1}
)

driver = webdriver.Chrome(options=option, service=ChromeService())
```

### Database Connection
A connection to PostgreSQL is established using SQLAlchemy:
```python
from sqlalchemy import create_engine
engine = create_engine('postgresql://postgres:*Your_Database_Password*@localhost:5432/DIY')
```

## Notes
- Make sure your PostgreSQL server is running and the 'DIY' database is created.
- Always keep your database credentials secure. Consider using environment variables or a config file.

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

