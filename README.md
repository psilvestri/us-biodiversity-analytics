# US Biodiversity Analytics Warehouse

## Overview

The **US Biodiversity Analytics Warehouse** is an end-to-end analytics engineering project that models nationwide species observation data into a structured, analytics-ready dimensional warehouse.

This project ingests raw public biodiversity datasets, transforms them using SQL-based modeling in BigQuery, and produces validated KPIs such as species richness and year-over-year biodiversity change across the United States.

The goal is to demonstrate production-grade analytics engineering practices using real-world, large-scale public data.

---

## Project Objectives

- Ingest raw US species observation data from public biodiversity datasets
- Normalize and standardize messy event-level data
- Design a dimensional warehouse model (fact and dimension tables)
- Implement structured transformation layers
- Build validated biodiversity KPIs
- Apply data quality testing and integrity checks
- Deliver analytics-ready datasets for BI consumption

---

## Data Sources

Public datasets used in this project include:

- **Global Biodiversity Information Facility (GBIF)** – US-filtered species observations  
- **US Census Bureau** – Geographic reference data (state and county mappings)

Future versions may incorporate climate data from NOAA.

---

## Architecture

This project follows a modern analytics engineering layered architecture:

### 1. Raw Layer (Bronze)
- Raw CSV/JSON biodiversity datasets loaded into BigQuery  
- No transformations applied  

### 2. Staging Layer (Silver)
- Data cleaning and normalization  
- Standardized timestamps  
- Valid coordinate filtering  
- Species name normalization  
- Geographic mapping to US states/counties  

### 3. Analytics Layer (Gold)

Dimensional warehouse design including:

#### Dimension Tables
- `dim_species`
- `dim_location`
- `dim_date`

#### Fact Tables
- `fct_species_observations`

Derived metrics include:
- Species richness by state  
- Year-over-year biodiversity change  
- Observation volume trends  

---

## Tech Stack

- **BigQuery** – Data warehouse  
- **SQL (GoogleSQL)** – Transformation logic  
- **dbt Core** – Model orchestration and testing  
- **Python** – Data ingestion and preprocessing  
- **Looker Studio** – Dashboarding  
- **GitHub** – Version control and CI  

---

## Data Modeling Approach

This warehouse uses a dimensional modeling approach:

- Fact table capturing species observations  
- Conformed dimensions for species, location, and time  
- Structured transformation layers separating raw, staging, and analytics models  
- KPI logic implemented in analytics models  

The design supports scalable trend analysis, geographic rollups, and future climate integrations.

---

## Data Quality & Testing

Data validation includes:

- `NOT NULL` constraints on primary keys  
- Referential integrity between fact and dimension tables  
- No future observation dates  
- No invalid geographic keys  
- Observation counts must be non-negative  

Testing ensures reliability and trust in downstream biodiversity metrics.

---

## Example KPIs

- **Species Richness Index** (distinct species per state per year)  
- **Year-over-Year Biodiversity Change**  
- **Top Observed Species by Region**  
- **Observation Growth Trends**  

---

## Future Enhancements

- Climate data integration (temperature and precipitation)  
- Habitat and land cover modeling  
- Incremental data loading  
- Partitioned tables for performance optimization  
- CI/CD pipeline for automated model validation  

---

## Why This Project

This project demonstrates:

- End-to-end analytics engineering workflow  
- Real-world messy data normalization  
- Dimensional modeling design  
- SQL transformation logic  
- Data quality enforcement  
- Business-ready KPI construction  

---

## Author

**Peter Silvestri**  
Analytics Engineer | Data Modeling | Marketing & Product Analytics  
**Peter Silvestri**  
Analytics Engineer | Data Modeling | Marketing & Product Analytics  
