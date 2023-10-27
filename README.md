# Web Scraper and Story Extractor README

## Overview

This is a repo that serves as example for the corresponding blog post I wrote covering this tutorial.

This script provides a utility to scrape web pages and extract structured content from them. It uses libraries like BeautifulSoup for HTML parsing, Playwright for web page interactions, and OpenAI's GPT model for structured data extraction from the scraped content.

## Prerequisites:

- Python 3.8+
  
## Installation Instructions:

1. First, make sure you have Python 3.8 or newer installed.
   
2. It's recommended to use a virtual environment for the project. Here's how you can set it up:

   ```bash
   # Install virtualenv
   pip install virtualenv
   
   # Create a new virtual environment named 'venv' using Python 3.11
   virtualenv venv -p python3.11
   
   # Activate the virtual environment
   source venv/bin/activate  # On Windows, use: venv\Scripts\activate
   ```

3. Install the required packages using the provided `requirements.txt`:

   ```bash
   pip install -r requirements.txt
   ```

## Environment File:

You should set up an `.env` file in the root directory of the project for any environment variables that the script may use. Here's an example structure for the `.env` file:

```
# .env example
OPENAI_API_KEY==YourValue
# Add other environment variables as needed
```

Make sure to replace `OPENAI_API_KEY` with the actual environment variables you need and provide the appropriate values.

## Usage:

1. Ensure you have the necessary environment variables set in a `.env` file.
2. Run the script and provide the necessary arguments.

```bash
python scraper.py --url "https://www.npr.org" --selector "[class~="story-web"]"
```

## Command-Line Arguments:

- `url`: The URL to scrape content from. Example: `"https://www.npr.org"`
- `--selector`: (Optional) The CSS selector to identify the elements to extract. Default is `[data-component-name='card']`. Example: `[class~='story-wrap']`

## Output:

The script will generate a CSV file named based on the parsed domain of the provided URL (e.g., for "https://www.npr.org", the file will be named `www_npr_org.csv`). This file will contain the extracted structured content.

## Dependencies:

Ensure you have the following libraries installed or listed in your `requirements.txt`:

- `argparse`
- `pprint`
- `json`
- `csv`
- `BeautifulSoup`
- `playwright`
- `langchain.prompts`
- `langchain.text_splitter`
- `langchain.chat_models`
- `langchain.chains`
- `dotenv`
- `urllib`

## Note:

Always ensure you have permission to scrape a website and respect its `robots.txt` file and terms of service.
