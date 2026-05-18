# An Empirical BI-Based Analytical Framework for Global Business Performance and Supply Chain Optimization

## 📝 Academic Project Overview
* **Researcher:** Pham Xuan Huyen
* **Date of Birth:** January 20, 2004
* **Specialization:** Applied Mathematics and Informatics
* **Institution:** University of Science (VNU-HCM)
* **Core Stack:** Power BI Desktop, Power BI Cloud Service, DAX, Power Query
* **Project Artifacts:** [Executive Summary Portfolio (PDF)](./Business%20Performance%20Analysis%20Dashboard.pdf) | Technical Source File (`.pbix`)

---

## 1. Abstract & Problem Statement

### 1.1. Abstract
This research introduces a centralized Business Intelligence (BI) framework designed to synthesize, model, and analyze large-scale, multidimensional transactional records from a global retail enterprise. Operating across 6 geographical regions (United States, Australia, United Kingdom, Germany, France, Canada) and spanning a 4-year temporal horizon (2016–2019), the system extracts granular data points to diagnose financial health, evaluate category velocity, and discover supply chain inefficiencies.

### 1.2. Problem Statement
Modern enterprises face extreme administrative latency due to fragmented, unnormalized relational data. The core challenge lies in mapping the complex, non-linear interactions between three specific vectors:
* **Spatial Vector ($\mathbb{S}$):** Multilingual, geographically dispersed sales channels.
* **Temporal Vector ($\mathbb{T}$):** Longitudinal transaction histories vulnerable to seasonality.
* **Structural Product Vector ($\mathbb{P}$):** Disparate margins across Accessories, Bikes, and Clothing categories.

---

## 2. Data Architecture & ETL Methodology

### 2.1. Extract - Transform - Load (ETL) Pipeline
To guarantee mathematical correctness and structural integrity, raw unstructured inputs were ingested and refined using Power Query engine via the following pipeline:
1. **Data Sanitization:** Imputation of missing structural fields and elimination of duplicate indices to prevent statistical inflation.
2. **Type Coercion & Normalization:** Forcing relational constraints on numerical fields and mapping coordinate attributes to standardize Geographic Information System (GIS) visualization inputs.
3. **Granularity Splitting:** Decomposing temporal timestamps into independent categorical dimensions (Year, Quarter, Month) to construct highly optimized hierarchy axes.

### 2.2. Relational Data Modeling (Star Schema)
To decouple operational overhead and minimize query latency ($O(1)$ to $O(\log N)$ structural execution), the database architecture was engineered around a rigid **Star Schema**:
* **Fact Table:** `Fact_Sales` - Central repository aggregating continuous transactional measurements (Sales volume, unit costs, gross revenue).
* **Dimension Tables:** `Dim_Products`, `Dim_Countries`, `Dim_Calendar` - Independent categorical tables establishing directional `1-to-Many` ($1 \rightarrow *$) topological joins to filter the central Fact matrix.

---

---

## 3. Mathematical Formulations & DAX Engineering

The analytical engine leverages Data Analysis Expressions (DAX) to evaluate real-time deterministic metrics. The computational logic is formalized as follows:

### 3.1. Total Cumulative Profit
Accumulated net margin derived via linear summation across the transactional domain:
$$\text{Total Profit} = \sum_{i=1}^{n} (\text{Sales Amount}_i - \text{Total Product Cost}_i)$$

### 3.2. Gross Profit Margin Ratio
Expressing the percentage efficiency of capital conversion:
$$\text{Profit Margin} = \left( \frac{\text{Total Profit}}{\text{Total Sales}} \right) \times 100\%$$

### 3.3. Year-Over-Year (YoY) Growth Coefficient
A time-intelligence vector translation computing the dynamic rate of change between the current temporal interval ($t$) and its historical shifted counterpart ($t-1$):
$$\text{YoY Growth} = \left( \frac{\text{Sales This Year}\_t - \text{Sales Last Year}\_{t-1}}{\text{Sales Last Year}\_{t-1}} \right) \times 100\%$$

*Production DAX Implementation:*
```dax
YoY Growth % = 
VAR SalesLastYear = CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Dim_Calendar'[Date]))
RETURN 
DIVIDE([Total Sales] - SalesLastYear, SalesLastYear, 0)
```

## 4. Empirical Results & Data Insights

### 4.1. Core Global Key Performance Indicators (KPIs)
Quantitative evaluation of the deployed analytical dashboard registers highly robust macromarket metrics:
* **Aggregate Sales Volume ($\text{TS}$):** `$29.36M`
* **Net Realized Profit ($\text{TP}$):** `$12.08M`
* **Calculated Operational Gross Margin:** `41.14%`
* **Logistical Throughput:** `27.66K` total processed orders
* **Longitudinal Momentum:** An exceptional Year-Over-Year growth rate of **`49.88%`**.

### 4.2. Structural Decomposition & Correlative Discoveries

 ### Asymmetry in Geographic Performance
 Spatial evaluation reveals that the **United States** and **Australia** act as the primary economic powerhouses for the enterprise. These two territories generate dominant profit densities, drastically overshadowing the consolidated yields of the European sectors (United Kingdom, Germany, France) and Canada.

 ### The Category-Profit Paradox
 Granular cross-filtering uncovers a profound non-linear correlation between transaction frequencies and net financial yields:
 * **United States Market:** The *Accessories* sector exhibits the maximum transaction frequency (highest order count). However, the **Bikes** sector controls high-density profit vectors, accounting for **over 90%** of net national profit.
 * **Australian Market:** Conversely, no paradox is observed in Australia; **Bikes** maintain absolute dominance, simultaneously leading both logistical throughput (order volume) and capital yield.

###  Temporal Seasonality and Macro-waves
 Time-series inspection reveals a highly predictable, recurring seasonal macro-wave. Gross revenue and net profit systematically display asymmetric distribution, consistently peaking during the **latter half of each fiscal year (Q3 and Q4)**, revealing rigid cyclical buying behavior.

---

## 5. Strategic Recommendations & Decision Support

Based on the empirical findings generated by the BI framework, the following prescriptive directives are proposed to support data-driven decision-making:

### 5.1. Target Capital Reallocation
* **Action:** Shift `15% to 20%` of generalized marketing and supply chain operating budgets directly into the **Bikes** inventory pipeline, specifically targeting the high-yielding US and Australian distribution channels.
* **Justification:** Optimizes return on equity by backing high-density profit vectors rather than raw transaction volumes.

### 5.2. Cost-Volume-Profit (CVP) Structural Audit
* **Action:** Conduct an immediate operational audit on the pricing models and production costs of the *Accessories* and *Clothing* categories across lower-performing European sectors.
* **Justification:** Eliminates the "high-throughput, low-yield" drag, expanding the overall corporate net margin profile.

### 5.3. Predictive Supply Chain Synchronization
* **Action:** Establish a systematic seasonal safety stock buffer for high-demand components at the terminal phase of **Quarter 2** annually.
* **Justification:** Pre-emptively mitigates systemic logistics bottlenecks and inventory stockouts during the high-velocity purchasing waves identified in Quarters 3 and 4.
