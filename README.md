# Lex Fridman Podcast Data Scraper

[![Python 3.6+](https://img.shields.io/badge/python-3.6+-blue.svg)](https://www.python.org/downloads/)
[![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=flat&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A Jupyter Notebook-based project that scrapes and analyzes data from the Lex Fridman Podcast, combining information from multiple sources including the official website, YouTube, Wikipedia, and Wikidata. The notebook generates a structured dataset suitable for analysis and research purposes.

## Features

* **Web Scraping:**
  * Extracts episode links from the Lex Fridman website using BeautifulSoup
  * Handles dynamic content loading

* **YouTube Integration:**
  * Leverages YouTube Data API v3 for comprehensive video metadata
  * Retrieves metrics like views, likes, and publish dates
  * Fetches video descriptions and episode details

* **Transcript Processing:**
  * Downloads episode transcripts using `youtube_transcript_api`
  * Cleans and formats caption data
  * Processes English language transcripts
  * Identifies top 5 keywords per episode using frequency analysis
  * Excludes common stop words and irrelevant terms

* **Guest Information:**
  * Scrapes biographical data from Wikipedia and Wikidata
  * Collects information such as:
    * Nationality
    * Profession(s)
    * Birth year
    * Death year (if applicable)

* **Data Management:**
  * Implements error handling for failed requests
  * Standardizes data formats for consistency
  * Exports to CSV with proper encoding (`Lex Fridman Podcast Episodes.csv`)

## Project Structure

```
lex/
├── Lex Fridman Podcast Webscraping.ipynb    # Main Jupyter Notebook containing the scraping code
├── requirements.txt                         # Project dependencies
└── README.md                                # Project documentation
└── Lex Fridman Podcast Episodes.csv         # Project csv output
```

## Requirements

### System Requirements
* Python 3.6 or higher
* Jupyter Notebook/JupyterLab
* Internet connection
* YouTube Data API key

### Dependencies
Install required packages using:
```bash
pip install -r requirements.txt
```

Key dependencies:
* `jupyter`
* `requests`
* `beautifulsoup4`
* `pandas`
* `numpy`
* `youtube_transcript_api`
* `google-api-python-client`

## Installation

1. Clone the repository:
```bash
git clone https://github.com/AhmedAtwaAli/lex.git
cd lex
```

2. Create and activate a virtual environment (recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Set up YouTube API credentials:
   * Go to [Google Cloud Console](https://console.cloud.google.com)
   * Create a new project and enable YouTube Data API v3
   * Create credentials (API key)
   * Add your API key to the notebook when prompted

## Usage

1. Ensure you have set up your YouTube API key.

2. Start Jupyter Notebook:
```bash
jupyter notebook
```

3. Open `Lex Fridman Podcast Webscraping.ipynb` in your jupyter notebook IDE.

4. Run the notebook:
   * You can run all cells at once using the "Run All" button
   * Or run cells individually by pressing Shift+Enter
   * Make sure to insert your YouTube API key in the designated cell

The notebook will:
- Scrape the Lex Fridman website for episode links
- Fetch YouTube metadata and transcripts
- Gather guest information
- Generate a CSV file with the compiled data

## Output Format

The notebook generates a CSV file with the following columns:
* `episode_number`
* `title`
* `guest_name`
* `publish_date`
* `views`
* `likes`
* `top_keywords`
* `guest_nationality`
* `guest_profession`
* `guest_birth_year`
* `guest_death_year`
* `transcript`
* `description`

* `yt_url`: URL of the YouTube video
* `number`: Episode number
* `guest`: Guest name
* `nationality`: Guest nationality
* `profession`: Guest profession
* `birth_year`: Guest birth year
* `death_year`: Guest death year (if applicable)
* `birth_year_estimated`: If birth year is estimated or not
* `summary`: Brief summary of the content
* `description`: Detailed description of the content
* `upload_date`: Date the video was uploaded
* `duration`: Duration of the video (ISO 8601 format e.g., "PT1H23M45S")
* `duration_minutes`: Duration in minutes
* `views`: Number of views
* `likes`: Number of likes
* `comments_count`: Number of comments
* `tags`: Keywords or tags associated with the video
* `top_five_words`: Top five said words from the content
* `favorite_count`: Number of favorites
* `region_restriction`: Any regional restrictions on the video
* `thumbnail_url`: URL of the video thumbnail
* `captions_availability`: Availability of captions

## Contributing

Contributions are welcome! Please feel free to:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/YourFeature`)
3. Make your changes
   * Add new analysis cells
   * Improve existing code
   * Add documentation
4. Commit your changes (`git commit -m 'Add some feature'`)
5. Push to the branch (`git push origin feature/YourFeature`)
6. Open a Pull Request

When contributing to the notebook:
* Keep cells well-documented with markdown cells
* Test all cells before committing
* Clear all outputs before committing
* Consider adding error handling for robustness

## Disclaimer

This notebook is intended for educational and personal use only. Please be mindful of:
* YouTube's terms of service and API quotas
* Wikipedia's and Wikidata's usage policies
* Potential copyright restrictions on transcripts
* Rate limiting and responsible scraping practices

The accuracy of biographical data scraped from Wikipedia and Wikidata is not guaranteed. Always verify critical information from primary sources.

## Acknowledgments

* Lex Fridman for creating valuable content
* YouTube API Documentation
* Wikipedia and Wikidata communities
* Contributors to the dependencies used in this project
