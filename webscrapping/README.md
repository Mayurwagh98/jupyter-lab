# Web Scraping & APIs

Notebooks covering how to pull data from the web — scraping HTML pages with **requests + BeautifulSoup**, handling pagination, and consuming a **REST API** as JSON.

## Contents

| File | Purpose |
|------|---------|
| `web_scraping.ipynb` | Scrape a country listing, parse it, and export to CSV |
| `assignment1.ipynb` | Paginated scraping of quotes with tag filtering |
| `api.ipynb` | Fetch data from a REST API and load JSON into a DataFrame |
| `scrapped_data.html` | Saved raw HTML from the country page |
| `quotes_data/` | Saved HTML for each scraped quotes page (`quotes_data_1..10.html`) |
| `cleaned_data.csv` | Parsed country/population output |

## Notebook Details

### web_scraping.ipynb — Basic Scraping
- Fetches a page with `requests.get`, checks the status code, and saves the raw HTML locally.
- Parses it with **BeautifulSoup** (`lxml` parser).
- Extracts country names (`find_all("h3")`) and populations (`find_next`, CSS `select`).
- Builds a pandas DataFrame and exports to `cleaned_data.csv`.

### assignment1.ipynb — Pagination + Filtering
- Loops through paginated URLs (`.../page/{n}/`) until no more quotes are found, saving each page's HTML.
- Re-parses the saved files, extracts quote text, author, and tags with CSS selectors, and keeps only quotes tagged `"life"`.

### api.ipynb — Consuming a REST API
- Calls a public REST API with `requests.get`.
- Parses the JSON response (`res.json()`) and flattens it into a DataFrame with `pd.json_normalize`.

## Concepts Covered
- HTTP requests with the `requests` library and status-code checks
- Saving and reading raw HTML
- Parsing HTML with BeautifulSoup (`find_all`, `find_next`, `select`, `select_one`, `get_text`)
- CSS selectors for targeted extraction
- Handling pagination with loops and stop conditions
- Filtering scraped records by attribute (tags)
- Working with REST APIs and JSON (`res.json()`, `pd.json_normalize`)
- Exporting results to CSV with pandas

## Requirements
```bash
pip install requests beautifulsoup4 lxml pandas
```

## Usage
Open a notebook in Jupyter and run top to bottom. The scraping notebooks write HTML into this folder (`assignment1.ipynb` expects a `quotes_data/` subfolder to exist). Note: scraping requires a live internet connection and depends on the target sites remaining available.
