# Cyclistic Bike-Share Data Analysis

## Project Overview

This project analyzes 12 months of Cyclistic bike-share trip data to understand how annual members and casual riders use bikes differently. The analysis follows the structured **six-phase data analytics process** (Ask, Prepare, Process, Analyze, Share, Act) to deliver actionable insights for the Cyclistic executive team.

**Business Task:** How do annual members and casual riders use Cyclistic bikes differently?

**Stakeholders:** Lily Moreno (Cyclistic Marketing Director) and the Cyclistic Executive Team

---

## Project Structure

```
Data Analytics - Study Case/
├── README.md                          # Project documentation (this file)
├── analysis.ipynb                     # Main analysis notebook
├── data/
│   ├── raw/                           # Original monthly data files
│   │   ├── 202501-divvy-tripdata.csv  # January 2025
│   │   ├── 202502-divvy-tripdata.csv  # February 2025
│   │   ├── ... (through December 2025)
│   │   └── 202512-divvy-tripdata.csv  # December 2025
│   └── processed/                     # Cleaned and aggregated data
│       ├── 2025-divvy-tripdata.csv    # Merged annual dataset
│       └── cyclistic_summary_statistics.csv  # Aggregated statistics for visualization
└── deliverables/                      # Comprehensive analysis reports
    ├── deliverable_1_ask.ipynb        # Phase 1: Business context & questions
    ├── deliverable_2_prepare.ipynb    # Phase 2: Data sources & structure
    ├── deliverable_3_process.ipynb    # Phase 3: Data cleaning & transformation
    ├── deliverable_4_analyze.ipynb    # Phase 4: Trends & insights
    ├── deliverable_5_share.ipynb      # Phase 5: Visualizations & findings
    ├── deliverable_6_act.ipynb        # Phase 6: Recommendations
    └── portfolio_introduction.ipynb   # Executive summary for portfolio
```

---

## Getting Started

### Prerequisites

- Python 3.7+
- Jupyter Notebook or JupyterLab
- Required packages: `pandas`, `matplotlib`, `seaborn`

### Installation

1. Clone or download this project to your local machine
2. Install dependencies:

   ```bash
   pip install pandas matplotlib seaborn jupyter
   ```

3. Navigate to the project directory:

   ```bash
   cd "Data Analytics - Study Case"
   ```

4. Launch Jupyter:
   ```bash
   jupyter notebook
   ```

---

## Analysis Workflow

### Phase 1: ASK

**File:** `deliverable_1_ask.ipynb`

Define the business problem and key questions:

- How do member and casual rider behaviors differ?
- What patterns emerge in usage across days, seasons, and hours?

### Phase 2: PREPARE

**File:** `deliverable_2_prepare.ipynb`

Acquire and understand the data:

- 12 months of Divvy trip data (January - December 2025)
- 13 columns per record: trip ID, start/end times, station locations, bike type, and user category
- Consolidated into annual dataset for efficient analysis

### Phase 3: PROCESS

**File:** `deliverable_3_process.ipynb`

Clean and transform data:

- Convert timestamps to datetime objects
- Calculate ride duration (in minutes)
- Extract temporal features: day of week, month, hour
- Remove data quality issues (negative ride lengths, extreme outliers)
- **Quality check:** Removed entries with rides ≤ 0 minutes or > 24 hours

### Phase 4: ANALYZE

**File:** `deliverable_4_analyze.ipynb`

Identify patterns and trends:

- **Ride duration:** Members average shorter trips; casuals average longer
- **Weekly patterns:** Different usage across weekdays vs. weekends
- **Hourly trends:** Commute peaks reveal distinct usage patterns
- **Seasonal trends:** Usage fluctuates throughout the year
- **Bike preference:** Notable differences in bike type selection

### Phase 5: SHARE

**File:** `deliverable_5_share.ipynb`

Visualize findings:

- Total rides by day of week
- Average ride duration trends
- Hourly distribution (commute patterns)
- Monthly volume (seasonality)
- Bike type preferences by user group

### Phase 6: ACT

**File:** `deliverable_6_act.ipynb`

Strategic recommendations:

- Top 3 actionable insights for converting casual riders to members
- Marketing and operational strategies

---

## Key Findings

### Member Behavior

- **Shorter rides:** Members take significantly shorter trips (average: ~10-12 minutes)
- **Weekday-focused:** Peak usage during weekdays, suggesting commuting patterns
- **Morning & evening peaks:** Strong commute-time activity (7-9 AM, 5-7 PM)
- **Bike preference:** Balanced across bike types

### Casual Rider Behavior

- **Longer rides:** Casual riders take substantially longer trips (average: ~20-30 minutes)
- **Weekend-dominant:** Significant surge on weekends, indicating leisure usage
- **Afternoon peaks:** Relaxed usage pattern, no sharp commute peaks
- **Seasonal sensitivity:** Higher engagement during warmer months
- **Bike preference:** Preference varies by season and conditions

---

## Data Files

### Raw Data (`data/raw/`)

- 12 monthly CSV files with original Divvy trip records
- Each file contains ~500K-700K trip records
- Fields: ride_id, rideable_type, started_at, ended_at, start_station_name, end_station_name, member_casual, etc.

### Processed Data (`data/processed/`)

- **2025-divvy-tripdata.csv:** Merged annual dataset (~6-7M records) with calculated fields
- **cyclistic_summary_statistics.csv:** Pre-aggregated statistics for efficient visualization

---

## How to Use

1. **Run the main analysis:**

   ```
   Open analysis.ipynb and run all cells
   ```

2. **Review individual phases:**

   ```
   Open deliverables/ folder and review each phase sequentially
   ```

3. **Explore findings:**

   ```
   Run Phase 5 (deliverable_5_share.ipynb) to view visualizations
   ```

4. **Regenerate merged dataset (optional):**
   ```
   In analysis.ipynb Phase 2, uncomment the data loading code to recreate the annual CSV
   ```

---

## Technical Details

### Data Transformation

- **Ride Length:** `(ended_at - started_at) / 60` seconds → minutes
- **Day of Week:** Encoded as 1 (Sunday) through 7 (Saturday)
- **Temporal Features:** Extracted month and hour from timestamp

### Data Quality

- Removed negative/zero-length rides
- Removed rides longer than 24 hours (data errors)
- **Retained records:** ~99% of original data quality checks passed

### Visualizations

- **Tools:** Matplotlib & Seaborn
- **Color scheme:** Green (#2ecc71) for members, Red (#e74c3c) for casual riders
- **Style:** Clean whitegrid theme for professional presentation

---

## Recommendations for Stakeholders

Based on usage patterns analysis, recommend:

1. **Leisure Marketing:** Target weekend casual riders with flexible membership packages
2. **Commute Programs:** Leverage member commute patterns for corporate partnerships
3. **Seasonal Campaigns:** Adjust promotions based on monthly usage trends
4. **Experience Enhancement:** Tailor bike types and service levels by user category

---

## Files & Artifacts

| File                           | Purpose                               |
| ------------------------------ | ------------------------------------- |
| `analysis.ipynb`               | Main consolidated analysis (6 phases) |
| `deliverable_1_ask.ipynb`      | Business context document             |
| `deliverable_2_prepare.ipynb`  | Data acquisition & schema overview    |
| `deliverable_3_process.ipynb`  | Data cleaning procedures              |
| `deliverable_4_analyze.ipynb`  | Statistical analysis & aggregations   |
| `deliverable_5_share.ipynb`    | Visualizations & insights             |
| `deliverable_6_act.ipynb`      | Strategic recommendations             |
| `portfolio_introduction.ipynb` | Executive summary                     |

---

## Author Notes

This project demonstrates the complete data analytics workflow from business problem definition through actionable recommendations. It's designed as both a practical analysis for Cyclistic leadership and a portfolio project showcasing data analytics competencies.

**Analysis Period:** January 2025 - December 2025  
**Total Records Analyzed:** ~6-7 million bike trips  
**Data Quality:** 99%+ retention after cleaning

---

## Contact & Support

For questions about this analysis, refer to the specific deliverable notebooks or review the main `analysis.ipynb` for a consolidated walkthrough.

---

_Last Updated: May 2026_  
_Data Source: Cyclistic Bike-Share Trip Data (Divvy)_
