# AdventureWorks Sales & Performance Analysis (Power BI Project)

Professional, end-to-end business intelligence solution developed in Power BI to analyze global sales performance, product profitability, and customer distribution for the fictional enterprise AdventureWorks. 

The project leverages the modern **Power BI Project (.pbip)** format. This approach isolates the semantic model data from the report layout, enabling clean version control, Git tracking of individual tables via TMDL, and programmatic management of DAX measures.

---

## Key Project Stages

### 1. Data Extraction & Transformation (Power Query)
* Extracted and engineered raw CSV corporate data files (Sales, Customers, Products, Territory, Calendar).
* Standardized relational keys, established data profiles, and optimized query performance by removing redundant attributes.
* Implemented conditional routing and data cleansing rules to handle historical discrepancies.

### 2. Relational Data Modeling
* Designed and compiled a high-performance **Star Schema** data architecture.
* Maintained strict separation between the central **Fact Table** (`Sales`) and surrounding **Dimension Tables** (`Products`, `Customers`, `Territories`, `Calendar`).
* Deployed advanced relationship management (including handling multiple date associations via `USERELATIONSHIP`) and constructed clean data navigation hierarchies.

### 3. Advanced Analytical Logic (DAX)
* Formulated core business logic KPIs using modular, decoupled measure structures.
* Engineered comprehensive **Time Intelligence** metrics (YTD, Month-over-Month, Year-over-Year shifts, rolling targets).
* Utilized advanced context filtering via `CALCULATE`, `FILTER`, `ALL`, and `DIVIDE` to calculate dynamic target achievements and complex margin distributions safely.

---

## Dashboard Architecture & Page Breakdown

The dashboard is structured into **4 functional analytical perspectives**, accessible via an interactive, native navigation bar:

### 1. Executive Dashboard
Designed for high-level stakeholders to monitor total organizational growth and evaluate core operational channels.
* **Top-Level Metrics:** Displays crucial financial indicators
* **Revenue Trending:** A continuous timeline visualization mapping monthly sales trajectories alongside an overarching historical trend line.
* **Performance Indicators:** Dynamic monthly comparison modules capturing current status with MoM variance indicators.
* **Category Breakdown & Top Products:** Evaluates sales volume across core segments. Features a deep-dive "Top 10 Products" matrix displaying corresponding transaction counts, generated revenue, and individual product return thresholds.
* **Dynamic Highlights:** Conditional highlights surfacing the absolute highest-performing product category alongside the highest-risk product type based on returns.

### 2. Product Detail
An operational cockpit allowing product managers to isolate specific SKUs, track target achievements, and perform "What-If" scenario tracking.
* **Target Gauges:** Visualizes real-time performance against predefined operational benchmarks for the selected product.
* **What-If Scenario Simulation:** Incorporates a dynamic "Price Adjustment" slider parameter. This parameter drives a dual-line chart comparing historical *Total Profit* against a projected *Adjusted Profit* curve based on changing pricing strategies.
* **Dynamic Metric Selection:** Features an interactive radio-button parameter selection module allowing users to toggle the bottom trend chart between key metrics: Orders, Revenue, Profit, Returns, or Return %

### 3. Customer Detail
Provides customer experience and marketing teams with granular intelligence on customer lifetime value, engagement frequency, and demographics.
* **Customer Value KPIs:** Tracks high-level engagement through Unique Customers and an impactful average Revenue per Customer.
* **Demographic Segmentation:** Dual donut charts filtering total transaction volumes by income and professional occupations.
* **Historical Acquisition Growth:** A dual-mode line chart tracking the cumulative acceleration of either Total Customers or Revenue per Customer over a specified date scale.
* **Top 100 Customers Matrix:** A clean ledger highlighting the top 100 highest-value consumers by name, listing their exact order counts and overall revenue contribution.
* **Individual Customer Spotlight:** Dynamically surfaces the single highest-value client across the selected filter scope.

### 4. Map
A geographical mapping layer utilized by logistics and regional expansion teams to locate revenue clusters and market share density.
* **Global Revenue Mapping:** Implements a dark-themed geographic canvas charting total sales distributions across key territories.
* **Proportional Scaling:** Bubble markers adjust scale dynamically relative to regional financial performance.
* **Continent Filters:** Native, clean slicing buttons across the top header allow immediate, one-click isolation of regions.

---

## Repository Structure

```text
├── images/
    └── screenshots/    
├── raw data/           # Source CSV corporate datasets
└── reports/            # Core Power BI Project files (.pbip)
    ├── *.Report/       # Visual configurations, themes, bookmark logic, and page structures
    └── *.SemanticModel/# Semantic data model architecture, entity tables, relationships, and TMDL definitions