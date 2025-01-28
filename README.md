# PubMed Data Extraction Tool

## Overview
This repository provides a Python-based tool for extracting research article metadata from PubMed using the Entrez Programming Utilities (E-utilities). The tool allows users to search PubMed based on specific queries, retrieve detailed metadata (e.g., titles, authors, publication dates, and affiliations), and export the results to a CSV file for further analysis.

---

## Features
- Query PubMed with custom search terms.
- Fetch article metadata including:
  - Title
  - Authors
  - Publication date
  - Corresponding author email
  - Non-academic authors and company affiliations.
- Analyze and categorize non-academic authors and corporate affiliations.
- Export results to a CSV file.

---

## Requirements
Ensure the following Python libraries are installed:

- `requests`
- `biopython`
- `pandas`

You can install the dependencies using:
```bash
pip install requests biopython pandas
```

---

## Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/pubmed-data-extraction.git
   cd pubmed-data-extraction
   ```

2. Set your email address for the PubMed API:
   - Update the line in the script:
     ```python
     Entrez.email = "your_email@example.com"
     ```
   This ensures compliance with PubMed's usage policy.

---

## Usage
1. Define your query and the maximum number of results in the script:
   ```python
   query = "cancer immunotherapy[tiab] AND 2022:2023[dp]"
   max_results = 50
   ```

2. Run the script:
   ```bash
   python pubmed_extraction.py
   ```

3. The results will be saved as a CSV file (e.g., `pubmed_results.csv`) in the same directory.

---

## Functions
### 1. `fetch_pubmed_data(query, max_results=100)`
Fetches PubMed articles matching the query and extracts metadata.

### 2. `extract_company_affiliations(authors)`
Identifies non-academic authors and company affiliations from the list of authors.

### 3. `save_to_csv_and_download(papers, output_file="pubmed_results.csv")`
Saves extracted metadata to a CSV file.

---

## Example Output
The output CSV contains the following columns:
- `PubmedID`
- `Title`
- `Publication Date`
- `Authors`
- `Corresponding Author Email`
- `Non-academic Author(s)`
- `Company Affiliation(s)`

---

## Contribution
Contributions are welcome! Feel free to submit issues or pull requests to improve the tool.

---

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
