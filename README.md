OA Question Scraper (Codeforces)

This repository contains a Google Colab–based scraping pipeline to collect Codeforces coding problems and store them in MongoDB Atlas for use in Online Assessment (OA) platforms, interview practice systems, and AI-based question pipelines.

The scraper supports:
1. Fetching problems by rating range
2. Extracting problem metadata
3. Storing structured data in MongoDB
4. Fetching full problem pages using ZenRows (anti-bot friendly)

Features

1. Scrapes Codeforces problems using:
   a. Official Codeforces API
   b. HTML scraping with BeautifulSoup
2. Filters problems by difficulty (rating range) (e.g. 1100–1400)
3. Stores problems in MongoDB Atlas
4. Extracts:
   a. Problem title
   b. Contest ID & index
   c. URL
   d. Rating
   e. Tags
5. Uses ZenRows to bypass bot protection for full problem pages
6. Designed to act as a data ingestion layer for OA platforms and LLM-based systems

Tech Stack: Python,Google Colab, MongoDB Atlas, pymongo, BeautifulSoup, ZenRows API

Project Workflow

1. Connect to MongoDB Atlas
2. Scrape problem metadata
   a.Using Codeforces API
   b.Using HTML scraping
3. Filter problems by rating
4. Insert structured problem data into MongoDB
5. Fetch full problem pages using ZenRows

Data Stored in MongoDB

Each problem is stored in the following format:
{
  "title": "Problem Name",
  "url": "https://codeforces.com/contest/XXXX/problem/A",
  "contest_id": "XXXX",
  "index": "A",
  "rating": 1200,
  "tags": ["greedy", "math"]
}


How to Run (Google Colab)
1. Open Google Colab
2. Upload the notebook or copy the code
3. Install dependencies: !pip install pymongo requests beautifulsoup4 zenrows
4. Update MongoDB credentials:
   username = "your_username"
   password = "your_password"
5. Run the cells step-by-step

Notes on Credentials
1. MongoDB credentials are required for Atlas connection
2. ZenRows API key is required for scraping protected pages
3. Do NOT commit real credentials to public repositories
4. Use environment variables or placeholders for production

Use Cases
1. Online Assessment (OA) platforms
2. Interview preparation systems
3. Competitive programming datasets
4. AI/LLM-based question rephrasing pipelines
5. Coding practice platforms

Related Project
This scraper is part of a larger system:
AI-Based Online Coding Assessment Platform
Uses LLMs to rephrase questions and Judge0 for code execution

Future Improvements:
Add sample test case extraction
Track solved/unsolved problems
Role-based question mapping (SDE, DS, etc.)
Automatic deduplication
Scheduler-based scraping
