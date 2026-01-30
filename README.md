# Pooled Fund Gap Detection & Enrichment | Python Notebook Project

## Overview

This project is a solution to help the billing team that needs an automated process to identify pooled funds that exist in one source but are missing in another and then prepare a business‑ready file for downstream fee rule setup. Every month they have a list of currently active pooled funds and their series, the Revenue Center’s fee rules register and historical invoice metadata that can be used to enrich missing entries.

### Prerequisites

Python 3.9+

Pandas library

Jupyter Notebook (or any environment capable of running .ipynb files)


### Required Input Files

Place the following CSV files in a local directory:

- active_funds.csv
- fee_rules.csv
- billing_repository.csv

### Step-by-Step

- Clone the GitHub repository or unzip the project files.
- Open the Jupyter notebook.
- Update the files_path variable in config cell to point to the directory containing the input CSV files.
- Run the notebook from top to bottom.
- Review the generated output in the same directory chosen.
- Check summary metrics at the end of the notebook.

### Key Assumptions Made

- Fund and series matching is case‑insensitive across all sources.
- Used Billing data from most recent effective_date and highest invoice_id used when multiple records exist on same date (based on the fact that they were generated last)
- Same billing data applied to all series (As they were not split by series in Billing data)

### Follow‑Up Questions for the Business

- Should fund‑level fee rules be assumed to cover all series by default?
- Should enrichment be based on the most recent invoice, earliest invoice, or a specific billing period?
- Should inactive or closed funds be excluded earlier in the process?

### What I Would Improve or Add With More Time

- Introduce schema validation and data quality checks.
- Add Slowly Changing Dimensions Type 2 technique to better handle effective‑date logic to align billing enrichment with fund activity dates.
- Externalize configuration (paths, column mappings) into a config file.
- Convert the notebook into a reusable Python module or scheduled pipeline.
- Add logging.
- Optimize performance by using PySpark for larger monthly datasets.


### Tools Used and How They Helped

Python: Core language for implementing the automation logic.

Pandas: Enabled efficient data cleaning, normalization, joins, and comparisons across sources.

Jupyter Notebook: Allowed rapid prototyping, and visibility into intermediate steps.

GitHub: Version control and reviewer access.

AI: Eliminated the need to think about coding structures and sped up development.