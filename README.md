# My First Web Search Engine

This project is a basic web search engine created as part of the **DSAI 301 - Introduction to Python Programming** course at **Bogazici University**. It demonstrates key concepts in web crawling, indexing, and ranking, with Python as the programming language.

Special thanks to the teachings of **Asst. Prof. Dr. Huseyin Oktay Altun**.

---

## Project Overview

### Features:
1. **Web Crawling**:
   - Starts with a seed URL and recursively visits pages to build a list of links.
   - Extracts and cleans the content of visited pages.

2. **Indexing**:
   - Builds a searchable index of keywords from the crawled pages.

3. **Page Ranking**:
   - Implements a simple ranking algorithm using the concept of in-links and out-links.

4. **Search Functionality**:
   - Allows keyword searches with or without ranking.

---

## How It Works

### 1. Web Crawling
The `crawlWeb` function begins with a seed URL and uses the following steps:
- Fetches page content using `getPage`.
- Extracts links using `get_all_links`.
- Recursively visits links and avoids duplicates.

### 2. Building an Index
- The content is cleaned using `getclearpage`.
- Keywords are added to the index using `add_to_index` and `addPageToIndex`.

### 3. Ranking
- A graph of interconnections between pages is generated.
- Page ranks are computed using a dampening factor.

### 4. Searching
- The `lookup` function searches the index for keywords and ranks results using `computeRanks`.

---

## Running the Code

To run this project:
1. Open the `MyFirstWebSearchEngine.ipynb` file in Google Colab.
2. Modify the `seed_url` variable to your desired starting point.
3. Run all cells sequentially to crawl, index, rank, and search.

Example:
```python
seed_url = "https://example.com"
index, graph = crawlWeb(seed_url)
lookup(index, "keyword", graph, computeRanks)
