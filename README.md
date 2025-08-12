# AI-Scraper-
A powerful and user-friendly tool for extracting business information from Google Maps.
AI Scraper
AI Scraper is a Python-based web scraping backend designed to automate the scraping process from Google Maps. It uses an undetected Chrome driver to avoid bot detection, supports headless mode, and communicates real-time status messages between backend and frontend components.

Features
Scrapes Google Maps based on user-provided search queries.

Supports customizable output formats.

Headless mode for running without opening a visible browser window.

Handles driver initialization with retries.

Communicates progress and errors through a frontend-backend messaging interface.

Automatically manages the Chrome WebDriver using undetected_chromedriver.

Scrolls dynamically loaded content automatically during scraping.

Installation
Clone the repository:

bash
Copy
Edit
git clone https://github.com/khushikudade26/ai-scraper.git
cd ai-scraper
Install the required dependencies:

bash
Copy
Edit
pip install -r requirements.txt
Make sure the requirements.txt includes:

undetected-chromedriver

any other dependencies like selenium, etc.

(Optional) Set the Chrome WebDriver path in settings.py if you want to use a specific driver executable.

Usage
Instantiate the backend scraper with the required parameters:

python
Copy
Edit
from backend import Backend

search_query = "restaurants in New York"
output_format = "csv"  # or any supported format
headless_mode = 1      # 1 for headless, 0 to show browser

scraper = Backend(search_query, output_format, headless_mode)
scraper.mainscraping()
The scraper will open Google Maps with the specified search query, scroll through the results, and extract data accordingly.

Status messages and errors will be communicated to the frontend via the Communicator module.

Parameters
Parameter	Description
searchquery	The keyword or phrase to search for on Google Maps.
outputformat	Desired output file format (e.g., CSV, JSON).
headlessmode	Browser mode: 1 for headless mode, 0 to open a visible browser window.

Error Handling
The scraper retries Chrome driver initialization up to 3 times before raising an error.

If any scraping errors occur, they are caught and logged via the Communicator.

The driver closes gracefully even if unexpected errors occur.

Project Structure
backend.py - Contains the Backend class handling scraping logic and driver management.

scraper/ - Contains helper modules such as Scroller (for scrolling automation) and Communicator (for frontend-backend communication).

settings.py - Configuration file for driver executable path and other settings.

Contributing
Contributions are welcome! Feel free to open issues or pull requests for bug fixes or new features.

License
This project is licensed under the MIT License.
