# MediFlow: Medicine Procurement & Supply Chain Analytics

**Turning healthcare procurement data into smarter purchasing decisions.**

## Overview

MediFlow is a data analytics project designed to identify inefficiencies in medicine procurement and supply chains. It analyzes shipment costs, supplier performance, delivery timelines, and purchasing patterns to help healthcare organizations make more informed procurement decisions.

The project combines real-world pharmaceutical shipment data with a clearly labelled simulated inventory dataset to explore procurement costs, supply reliability, stockout risks, and medicine wastage.

## Problem Statement

Inefficient procurement can lead to higher purchasing costs, unreliable deliveries, inventory shortages, and medicines expiring before use.

MediFlow aims to answer four key questions:

- Which suppliers offer the best balance of cost and delivery reliability?
- Where do procurement and freight costs vary significantly?
- Which medicines or categories face higher supply risks?
- How can purchasing and replenishment decisions be improved using data?

## Objectives

- Analyze procurement spending and shipment-level costs.
- Evaluate supplier performance and delivery reliability.
- Identify purchasing patterns and potential supply-chain bottlenecks.
- Simulate inventory conditions to examine stockout and expiry risks.
- Translate analytical findings into actionable procurement recommendations.

## Dataset

### Primary dataset: Supply Chain Shipment Pricing Data

**Source:** [Kaggle — Supply Chain Shipment Pricing Data](https://www.kaggle.com/datasets/apoorvwatsky/supply-chain-shipment-pricing-data)

The dataset contains historical health-commodity shipment and pricing information, including pharmaceutical products and related logistics.

**Planned analysis variables** include product or commodity, supplier, shipment quantities, unit pricing, shipment dates, delivery information, and freight costs, subject to the fields available in the downloaded data.

### Supplementary dataset: Simulated Inventory Data

A synthetic dataset generated using Python will represent inventory movements, medicine demand, stock levels, reorder thresholds, and expiry dates.

This supplementary dataset will be used to explore stockout and expiry-related risks that cannot necessarily be measured directly from the historical shipment dataset.

**Data integrity note:** Real-world shipment records and simulated inventory records will remain clearly distinguished throughout the analysis.

## Tech Stack

| Tool | Purpose |
|---|---|
| Python | Data processing and exploratory analysis |
| Pandas | Data cleaning and transformation |
| PostgreSQL | Relational data storage and SQL analysis |
| SQL | Procurement KPIs and supplier comparisons |
| Tableau | Interactive procurement analytics dashboard |
| Faker | Generation of supplementary simulated data |

## Methodology

### 1. Data Collection and Preparation
- Download and inspect the public shipment dataset.
- Assess missing values, duplicate records, inconsistent formats, and data quality.
- Clean and transform relevant fields using Python and Pandas.
- Generate supplementary synthetic inventory data where required.

### 2. Database Design
- Load cleaned datasets into PostgreSQL.
- Design appropriate tables and relationships.
- Write SQL queries to aggregate procurement costs, compare suppliers, and analyze shipment performance.

### 3. Exploratory Data Analysis
Investigate procurement costs, supplier-level variation, freight expenditure, shipment timelines, and category-level purchasing patterns.

### 4. KPI Development

The analysis will explore the following metrics, where the required fields are available:

- **Total Procurement Spend:** Total recorded purchasing expenditure.
- **Average Unit Cost:** Average cost per unit, using an appropriate quantity-weighted calculation when needed.
- **On-Time Delivery Rate:** Percentage of eligible shipments delivered by their recorded expected dates.
- **Average Lead Time:** Average elapsed time between shipment or order initiation and delivery, based on available timestamps.
- **Freight Cost Share:** Freight expenditure as a proportion of relevant total shipment costs.
- **Stockout Rate:** Measured using simulated inventory data and a defined stockout methodology.
- **Expiry-Related Inventory Loss:** Estimated loss from simulated inventory reaching expiry before use.

### 5. Dashboard Development
Build an interactive Tableau dashboard featuring:

- Procurement spending trends
- Supplier performance comparisons
- Product- and category-level cost analysis
- Shipment delivery and lead-time analysis
- Simulated inventory health and expiry-risk indicators

### 6. Decision-Making and Recommendations
Use the findings to develop recommendations for supplier selection, purchasing prioritization, delivery-risk monitoring, and inventory replenishment.

Recommendations will be based on observed data patterns and explicitly stated assumptions rather than unsupported claims of cost savings.

## Expected Deliverables

- Cleaned and documented datasets
- Python notebooks for data preparation and exploratory analysis
- PostgreSQL schema and SQL analysis queries
- Interactive Tableau procurement dashboard
- A concise findings report with prioritized procurement recommendations

## Repository Structure

```text
MediFlow/
├── data/
│   ├── raw/
│   ├── processed/
│   └── simulated/
├── notebooks/
│   └── exploratory_data_analysis.ipynb
├── sql/
│   ├── schema.sql
│   └── procurement_analysis.sql
├── dashboard/
├── reports/
├── requirements.txt
└── README.md
```

The raw-data directory should contain only data that can legally be redistributed. Refer to the original source for access and usage terms.

## Getting Started

### Prerequisites
- Python 3.10 or a compatible version
- PostgreSQL
- Tableau Desktop or Tableau Public
- Git

### Setup

Clone the repository:

```bash
git clone <your-repository-url>
cd MediFlow
```

Create and activate a virtual environment:

```bash
python -m venv .venv
source .venv/bin/activate
```

On Windows, activate it using:

```bash
.venv\Scripts\activate
```

Install the required Python libraries:

```bash
pip install pandas numpy matplotlib seaborn jupyter faker sqlalchemy psycopg2-binary
```

Download the primary dataset from the linked source, place it in `data/raw/`, and configure your PostgreSQL connection locally. Do not commit database credentials or sensitive data.

Run the notebooks, execute the SQL scripts, and connect the processed outputs to Tableau as the project components are implemented.

## Limitations

- The primary dataset is historical and may not represent current pharmaceutical pricing or supplier performance.
- Findings depend on the completeness and quality of the source data.
- Stockout and expiry-related analysis will rely on simulated inventory data unless suitable real inventory data becomes available.
- Recommendations are analytical proposals, not validated operational outcomes.

## Project Status

**In development.** The project will be updated as data preparation, SQL analysis, dashboard development, and validation are completed.

## Learning Goals

MediFlow is designed to demonstrate practical data analysis, relational data modelling, KPI development, dashboarding, and evidence-based decision-making in a healthcare supply-chain context.
