# Scrape-IMDB-movie-rating-and-details



This Python script scrapes the top movies from IMDb's Top 250 Movies list using BeautifulSoup and parses JSON-LD data to extract detailed movie information such as title, IMDb URL, description, rating, and image URL. The extracted data is displayed in a structured format using pandas.

---

## Features
- Scrapes IMDb's Top 250 Movies list.
- Extracts movie details using the JSON-LD script embedded in the webpage.
- Converts the extracted data into a pandas DataFrame for easy analysis.

---

## Requirements

### Libraries
The script requires the following Python libraries:
- `pandas` for handling tabular data.
- `bs4` (BeautifulSoup) for parsing HTML.
- `requests` for making HTTP requests.
- `json` for parsing JSON data.

### Installation
Use the following commands to install the required libraries if they are not already installed:
```bash
pip install pandas beautifulsoup4 requests
```

---

## How to Use

1. **Clone or Download the Script**
   Save the script to your local machine as a `.py` file.

2. **Run the Script**
   Execute the script in your Python environment:
   ```bash
   python imdb_scraper.py
   ```

3. **Output**
   The script will display the top 5 movies in a pandas DataFrame format, including:
   - Movie Title
   - IMDb URL
   - Description
   - Rating
   - Image URL

---

## Code Overview

### Steps in the Script:
1. **Send an HTTP GET Request**  
   The script fetches the IMDb Top 250 Movies page using the `requests` library with appropriate headers to mimic a browser.

2. **Parse HTML Content**  
   The `BeautifulSoup` library parses the webpage content.

3. **Extract JSON-LD Data**  
   The embedded `application/ld+json` script tag contains structured movie data. The script extracts and parses this JSON data.

4. **Extract Movie Information**  
   The script iterates through the JSON data to extract key details (e.g., title, description, rating).

5. **Store Data in a DataFrame**  
   The collected data is stored in a pandas DataFrame for analysis and display.

---

## Sample Output

The first few rows of the DataFrame will look like this:
| Title             | IMDb URL                              | Description            | Rating | Image URL            |
|--------------------|---------------------------------------|------------------------|--------|-----------------------|
| The Shawshank ... | https://www.imdb.com/title/tt0111161/ | Two imprisoned men... | 9.3    | https://...shawshank |
| The Godfather     | https://www.imdb.com/title/tt0068646/ | The aging patriarch... | 9.2    | https://...godfather |

---

## Notes
- The script may stop working if IMDb changes its page structure or JSON-LD format.
- Ensure your IP is not blocked by IMDb for frequent requests. Use a proxy or set a delay if necessary.

---

## License
This project is licensed under the MIT License. Feel free to use and modify it as needed.
