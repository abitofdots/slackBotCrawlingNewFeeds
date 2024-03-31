# Grant Announcement Crawler

This project is a Python-based crawler designed to automatically scrape grant announcements from various websites and notify users via Slack. It employs Selenium for dynamic web pages and BeautifulSoup for static pages, facilitating comprehensive coverage across different types of web structures.

## Features

- **Dynamic and Static Page Handling**: Supports both dynamic pages that require interaction and static pages for straightforward scraping.
- **Scheduled Execution**: Runs at specified times to ensure up-to-date information is fetched without constant manual oversight.
- **Slack Integration**: Automatically sends notifications to a designated Slack channel, providing timely updates on new grant announcements.
- **Flexible Configuration**: Easily add or modify website configurations to tailor the crawler to specific needs.

## Getting Started

1. Ensure Python 3.7+ is installed.
2. Clone the repository.
3. Install dependencies: `pip install -r requirements.txt`.
4. Set up the `.env` file with your Slack API token and channel ID.
5. Run `python start.py` to start the scheduler and crawler.

## Key Files

The project consists of several key components outlined below:

- `start.py`: A scheduler script that triggers the main crawler at specified intervals, ensuring the crawler runs at pre-defined times throughout the day. It also manages logging and the execution schedule, adjusting for weekends.
- `src/main.py`: The core script that orchestrates the crawling process. It fetches website configurations, extracts new posts, logs them, and notifies a Slack channel about any new grant announcements.
- `src/websites_config.py`: Configuration file containing details of websites to be crawled, including URLs, selectors for scraping, and other parameters tailored to each site's structure.
- `src/fetch_methods/`: A directory containing various Python scripts (`useSelenium.py`, `useSeleniumCheckBox.py`, `useUrlQuery-x.py`, etc.), each implementing a specific method for fetching and processing website data.
