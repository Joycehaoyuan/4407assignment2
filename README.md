# 4407 Assignment 2

This repository contains the code for Assignment 2 of the 4407 course.

## Scripts 1: empty_cells

Identifies and counts empty cells in each column of the dataset.

### Features:
- Accepts any delimiter (e.g., `;`, `,`, or `TAB`)  
- Skips the header row and processes real data only  
- Outputs a list: column names + number of empty cells  
- Helps locate and quantify data quality issues before preprocessing

**Setup**
`chmod +x empty_cells`

**Usage**:
`./empty_cells <filename>`

**Example**:
`./empty_cells bgg_dataset.txt ";"`

**Output**:
Lists each column name followed by the number of empty cells found in that column.

## Script 2: preprocess

This script performs initial data cleaning for the raw dataset and sends the cleaned output to standard output (stdout).

### Features:
- Converts `;` separators to tab characters
- Converts Windows `\r\n` line endings to Unix `\n`
- Converts European decimal format (`,`) to `.` for floating-point numbers
- Removes non-ASCII characters (e.g., CO₂ becomes CO)
- Replaces missing IDs with unique new integer IDs continuing from the largest existing one

**Setup**
`chmod +x preprocess`

**Usage**:
`./preprocess <filename>`

**Example**:
`./preprocess sample.txt`

**Output**:
Sends a cleaned version of the input data to standard output

## Scripts 3: analysis
Performs statistical analysis on the cleaned dataset, such as computing yearly summaries.

### Features:
- Reads a cleaned .tsv file with tab-delimited columns
- Computes average and/or maximum renewable and coal generation grouped by year
- Outputs results in a clear tabular format

**Setup**
`chmod +x analysis`

**Usage**
`./analysis <filename>`

**Example**:
`./analysis sample.tsv`

**Output**:
Tabular summary printed to the terminal, showing statistics like average renewable generation per year.