# rename_tool

A Python CLI utility to rename files in a dataset based on a provided Excel mapping file and SOP (Standard Operating Procedure) file naming rules.

## Features
- Reads Excel mapping file (`mapping.xlsx`).
- Renames files following SOP format: [DocumentType]\_[ClientName]\_[TaxYear]_[Notes].pdf
- Validates `DocumentType` against SOP-approved list.
- Default **dry-run** mode (prints plan, does not change files).
- `--commit` mode to perform renames transactionally.
- Generates `summary.csv` and `rename_log_YYYYMMDD.txt`.
- Rollback mechanism if an error occurs during commit.
- Unit tests with pytest.

## Installation
   `pip install -r requirements.txt`

## Usage
- Dry-run
   `python -m rename_tool /path/to/demo_dataset mapping.xlsx`
- Commit changes
   `python -m rename_tool /path/to/demo_dataset mapping.xlsx --commit`