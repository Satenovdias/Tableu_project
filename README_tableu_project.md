# Tableau Project — Short-Term Rental Market Analysis

## Overview

This project is a Tableau-based analytical dashboard designed to explore pricing, listing distribution, geographic patterns, and time-based price dynamics in a short-term rental market.

The analysis combines listing-level information with calendar data to provide a multidimensional view of the rental market.

The project focuses on answering practical analytical questions such as:

- How does the average listing price change depending on the number of bedrooms?
- How many listings are available for different bedroom categories?
- How does the average price vary across ZIP codes?
- Which geographic areas have higher or lower average listing prices?
- How does the price-based metric labeled **"Revenue for year"** change throughout the year?
- How can price and listing distribution be compared across different parts of the market?

---

## Business Questions

### 1. Pricing by property size

**Question:** How does the average listing price vary with the number of bedrooms?

The `Avg price per bedroom` visualization compares the average price across different bedroom categories.

### 2. Listing distribution

**Question:** How many unique listings are available for each bedroom category?

The `Distinct count of bedroom listing` visualization uses a distinct count of listing IDs and groups the results by the number of bedrooms.

### 3. Price differences by ZIP code

**Question:** How does the average listing price differ between ZIP codes?

The `Price by zipcode` visualization compares average listing prices across ZIP codes.

### 4. Geographic price distribution

**Question:** Where are higher and lower average listing prices geographically concentrated?

The `Price per zipcode` visualization represents ZIP codes on a map and displays the corresponding average price.

### 5. Price dynamics throughout the year

**Question:** How does the metric labeled `Revenue for year` change over time?

The `Revenue for year` visualization uses calendar data and displays the sum of price at a weekly level.

The dashboard is configured to analyze the period from January through December 2016.

---

## Data Model

The Tableau workbook combines two data tables.

### Listings

Contains property- and host-level information, including:

- Listing ID
- Property type
- Room type
- Number of bedrooms
- Number of beds
- Number of bathrooms
- Accommodates
- ZIP code
- Latitude and longitude
- Listing price
- Minimum and maximum nights
- Availability
- Number of reviews
- Review scores
- Host information

### Calendar

Contains time-based listing information, including:

- Listing ID
- Date
- Availability
- Price

### Relationship

The two tables are joined using:

```text
Listings.id = Calendar.listing_id
```

The Tableau workbook uses an inner join between the two tables.

---

## Key Metrics

| Metric | Description |
|---|---|
| Average Price | Average listing price |
| Distinct Listing Count | Number of unique listings |
| Bedrooms | Number of bedrooms in a listing |
| ZIP Code | Geographic identifier used for price comparison |
| Weekly Price Sum | Sum of price at weekly granularity |
| Geographic Average Price | Average listing price by ZIP code |

---

## Dashboards & Visualizations

The Tableau workbook contains a dashboard built from five main worksheets:

### `Avg price per bedroom`

Shows the relationship between the number of bedrooms and average listing price.

### `Distinct count of bedroom listing`

Shows the number of unique listings for each bedroom category.

### `Price by zipcode`

Compares average listing prices across ZIP codes.

### `Price per zipcode`

Provides a geographic map of average listing prices by ZIP code.

### `Revenue for year`

Shows the weekly development of the price-based metric throughout 2016.

---

## Analytical Approach

The analysis focuses on four main dimensions:

**Property characteristics**

- Bedrooms
- Beds
- Bathrooms
- Property type
- Room type

**Pricing**

- Listing price
- Average price
- Price by ZIP code
- Weekly price aggregation

**Geography**

- ZIP code
- Latitude
- Longitude

**Time**

- Calendar date
- Weekly aggregation
- 2016 analysis period

This combination allows the project to examine the rental market from structural, geographic, pricing, and temporal perspectives.

---

## Tools & Technologies

- **Tableau** — data visualization and dashboard development
- **Microsoft Excel** — source data structure used by the Tableau workbook
- **Git / GitHub** — version control and project hosting
- **Git LFS** — storage of large Tableau and Excel files

---

## Repository Structure

```text
Tableu_project/
│
├── Tableau project.twbx
├── Tableau project.xlsx
├── .gitattributes
├── .gitignore
└── README.md
```

> The Excel file is included as a supporting data source for the Tableau workbook. The analytical presentation and visualizations are contained in the `.twbx` workbook.

---

## How to Use

### 1. Clone the repository

```bash
git clone https://github.com/Satenovdias/Tableu_project.git
```

### 2. Install Git LFS

```bash
git lfs install
```

### 3. Download the LFS files

```bash
git lfs pull
```

### 4. Open the Tableau workbook

Open:

```text
Tableau project.twbx
```

using Tableau Desktop.

---

## Git LFS

The repository uses **Git Large File Storage (Git LFS)** for large project files.

The following file types are tracked with Git LFS:

```text
*.twbx
*.xlsx
```

This allows large Tableau workbooks and datasets to be version-controlled without storing their full binary contents directly in the Git repository.

---

## Project Purpose

The main purpose of this project is to demonstrate how a rental-market dataset can be transformed into an interactive analytical dashboard.

The project demonstrates:

- Data modeling
- Joining listing and calendar data
- KPI development
- Geographic analysis
- Time-series analysis
- Price segmentation
- Tableau dashboard design
- Git and Git LFS project management
