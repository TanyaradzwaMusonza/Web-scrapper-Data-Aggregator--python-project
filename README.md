This Python script scrapes the top 10 latest job listings from https://vacancymail.co.zw/jobs/ and saves the extracted data to a CSV file. It is designed to run either manually or automatically on a daily schedule, with logging enabled to track activity and errors.

📌 Features
Scrapes up to 10 latest job posts from the site

Extracts key details including:

Job Title

Company Name

Location

Expiry Date

Job Description

Job Link

Saves job data to a dated .csv file

Logs activities and warnings to scraper.log

Can be scheduled to run daily at 8:00 AM

🧪 Requirements
Python 3.6+

Internet connection (to access the website)

📦 Dependencies
Install the required packages using pip:

bash
Copy

Edit
pip install requests beautifulsoup4 pandas schedule
🚀 Usage
1. Run Once Manually
To execute the scraper once:

bash
Copy

Edit
python web_scraper.py
The script will:

Scrape up to 10 jobs

Save them in a file like scraped_data_YYYY-MM-DD.csv

Log output to scraper.log

2. Run Automatically Every Day
To enable scheduling (runs daily at 8:00 AM):

Uncomment the line at the bottom of the script:

python
Copy

Edit
# schedule_scraping()
Then run:

bash
Copy

Edit
python web_scraper.py
🕗 The script will stay running and trigger scraping every day at 08:00.

📂 Output
CSV File: Saved in the same directory, named using the current date.
Example: scraped_data_2025-04-15.csv

Log File: Records errors, skipped items, and success messages in scraper.log.

🛡️ Error Handling
Skips job listings with missing or malformed data.

Logs warnings for each skipped listing.

Prints and logs an error if scraping fails altogether.

✏️ Customization Tips
Want more than 10 jobs? Update the if len(jobs) == 10: condition.

Want different cities in the filter? Modify the city list in:

python
Copy

Edit
elif any(city in text for city in ["Harare", "Bulawayo", "Mutare"]):
