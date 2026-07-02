# Nashville Housing Data Analysis

Analyzed Nashville real estate transaction data using SQL Server to clean messy property records and identify housing market trends. Used SQL queries for data preparation and Excel for storage and review.

## Table of Contents

1. Overview
2. Business Problem
3. Tools Used
4. Project Files
5. Data Fields
6. Cleaning Process
7. How to Use
8. Key Findings
9. Setup Instructions
10. Contact

## Overview

This project explores Nashville housing transactions to answer key business questions:
- What are property values across different neighborhoods?
- How have sale prices changed over time?
- What percentage of properties were vacant at sale?
- Which areas have the most expensive properties?

## Business Problem

Real estate professionals need clean, organized data to make informed decisions about property valuations and market trends. Raw housing data contains missing addresses, inconsistent formats, and duplicate records that prevent meaningful analysis.

## Tools Used

- SQL Server - Data cleaning and transformation
- Excel - Raw data storage and review
- T-SQL - Advanced queries (joins, CTEs, window functions)
- Git - Version control

## Project Files

**Nashville Housing Data.xlsx** (24.5 MB)
- Raw transaction records with property and owner information
- Fields: ParcelID, SaleDate, SalePrice, PropertyAddress, OwnerAddress, SoldAsVacant

**Nashville_SQL_Cleaning.sql** (3.5 KB)
- SQL cleaning script with 6 transformation steps
- Includes: date conversion, address splitting, duplicate removal, standardization

## Data Fields

| Field | Description | Example |
|-------|-------------|---------|
| UniqueID | Unique record identifier | 42521 |
| ParcelID | Property identification | 107 04 0 521.00 |
| SaleDate | Transaction date | 2013-04-09 |
| SalePrice | Sale amount | $465,000 |
| PropertyAddress | Property street location | 1234 Main St |
| OwnerAddress | Owner residence | 5678 Oak Ave |
| SoldAsVacant | Vacant status (Y/N) | Y or N |

## Cleaning Process

### Step 1: Convert Date Format
- Convert datetime to date format for consistency

### Step 2: Fill Missing Addresses
- Match properties by ParcelID to populate NULL address values

### Step 3: Split Address Data
- Separate property address into street and city components
- Separate owner address into street, city, and state

### Step 4: Standardize Vacant Status
- Convert Y/N to Yes/No for clarity

### Step 5: Remove Duplicates
- Use ROW_NUMBER() to identify and filter duplicate records

### Step 6: Drop Unused Columns
- Remove original messy columns after transformation

## How to Use

### Step 1: Set Up Database
```sql
-- Create database in SQL Server
CREATE DATABASE NashvilleHousing;
-- Import Nashville Housing Data.xlsx as table: NashvilleHousing
```

### Step 2: Run Cleaning Script
```sql
-- Execute Nashville_SQL_Cleaning.sql in SQL Server Management Studio
-- This applies all 6 transformation steps
```

### Step 3: Verify Cleaned Data
```sql
SELECT * FROM NashvilleHousing;
```

### Step 4: Export for Analysis
- Export cleaned data to Excel or visualization tool (Power BI, Tableau)
- Use for further analysis or reporting

## Key Findings

- Address data standardized and split into usable components
- Vacant properties identified and flagged for analysis
- Duplicate records removed ensuring data accuracy
- Date formats normalized for time-series analysis
- Property locations organized by city for geographic analysis

## Setup Instructions

### Requirements
- SQL Server 2016 or later
- Microsoft Excel
- Git

### Step-by-Step

1. Clone repository
```bash
git clone https://github.com/Pradniu/Nashville-Housing-Data-Analysis.git
```

2. Open SQL Server Management Studio
   - Create new database: NashvilleHousing
   - Right-click Tasks > Import Data
   - Select Nashville Housing Data.xlsx
   - Import as table: NashvilleHousing

3. Execute cleaning script
   - Open Nashville_SQL_Cleaning.sql
   - Run all queries in sequence

4. Verify results
```sql
SELECT * FROM NashvilleHousing;
```

5. Export for analysis
   - Use cleaned data for Power BI or Tableau dashboards
   - Run custom queries for specific insights

## SQL Techniques Demonstrated

- String Functions (SUBSTRING, PARSENAME, REPLACE)
- JOIN operations for data enrichment
- CASE statements for conditional logic
- Window Functions (ROW_NUMBER())
- ALTER TABLE for schema modifications
- CTE for organized query logic

## Data Quality

- All NULL addresses populated using matching logic
- Date formats standardized across dataset
- Duplicate detection using composite keys
- Vacant property values standardized
- Address components split for geographic analysis

## Contributing

Fork the repository
Create feature branch
Commit changes
Push to branch
Open Pull Request

## License

MIT License - See LICENSE file for details

## Contact

GitHub: Pradniu
Repository: Nashville-Housing-Data-Analysis

Questions or suggestions? Open a GitHub Issue.

## Quick Start Checklist

- Clone repository
- Review data files in Excel
- Create NashvilleHousing database in SQL Server
- Import Excel file as table
- Execute SQL cleaning script
- Export cleaned data
- Use for analysis or dashboards

---

**Project Status:** Complete  
**Last Updated:** 2025
