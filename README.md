# Web Scraper + Regular Expressions (Python)

A Python web scraper that turns messy HTML into clean, structured data. It fetches web pages with `requests`, parses the HTML with `BeautifulSoup`, and uses regular expressions to extract **email addresses, dates and prices**.

## What it does

1. **Fetch:** downloads a page's HTML with `requests` and checks the response status.
2. **Parse:** loads the HTML into `BeautifulSoup` and pulls out the visible text.
3. **Extract:** runs regex patterns over the text to find:
   - Email addresses (e.g. `name@example.com`)
   - Dates (e.g. `2024-07-23`, `07/23/2024`)
   - Prices (e.g. `$19.99`, `€5`)
4. **Structure:** collects the matches into lists or a table ready for further analysis.

## Tools

- Python 3
- `requests`: HTTP requests
- `beautifulsoup4`: HTML parsing
- `re`: regular expressions
- Jupyter Notebook

## How to run it

```bash
git clone https://github.com/Christos005/Python_Project.git
cd Python_Project
pip install requests beautifulsoup4 notebook
jupyter notebook "Web Scraper + Regular Expression Project.ipynb"
```

Run the cells from top to bottom. To scrape a different page, change the URL in the first cells.

## Troubleshooting

| Problem | Likely cause | Fix |
|---|---|---|
| `ModuleNotFoundError: No module named 'bs4'` | BeautifulSoup isn't installed | `pip install beautifulsoup4` |
| Status code `403` or `429` | The site blocks or rate-limits scripts | Add a `User-Agent` header, slow down requests, or try another page |
| No matches found | The content is loaded with JavaScript, or the pattern doesn't fit the page's format | View the page source to confirm the text is in the HTML, then adjust the regex |
| Too many false matches | The regex pattern is too broad | Tighten the pattern, require a currency symbol for prices |

## What I learned

- Writing and testing regex patterns for real-world, inconsistent text
- Handling HTTP responses and errors
- Turning unstructured web content into data that's ready for analysis

## Notes

Only scrape pages you're allowed to scrape. Check the site's `robots.txt` and terms of use.

---
**Author:** Christos Georgoudis · [GitHub](https://github.com/Christos005)
