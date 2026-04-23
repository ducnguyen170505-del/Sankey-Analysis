# Customer Journey Sankey Analysis Project

This project analyzes customer navigation behavior across the e-commerce website to identify key user flow patterns, drop-off points, and high-performing conversion paths using Sankey visualization.

---

## Objectives

- Understand how users move through different pages of the website  
- Identify the most common customer journey paths (e.g., landing → product → checkout)   
- Evaluate which traffic sources and landing pages lead to higher conversions  
- Support optimization of website structure and marketing funnel performance  

---

## Dataset

- **Source:** Ecommerce dataset from Xóm Data - a group of members having passion with Data  
- **Structure:** Each row represents a pageview event within a user session  

### Key Columns:
- `website_session_id`: unique session identifier  
- `pageview_id`: sequential page visit ID  
- `created_at`: timestamp of pageview  
- `pageview_url`: visited page  
- `utm_source`: traffic acquisition source  

---

## Methodology

### 1. Data Preprocessing
- Cleaned session-level clickstream data  
- Removed invalid or incomplete sessions  
- Sorted pageviews by `website_session_id` and `created_at`  

### 2. Journey Construction
- Identified landing page (first touch) for each session  
- Reconstructed user navigation paths based on pageview sequence  

### 3. Flow Aggregation
- Built transitions between pages:
  - `utm_source → landing_page`
  - `landing_page → product_page`
  
### 4. Sankey Data Preparation
- Created edge list format:
  - `source`
  - `target`
  - `value` (number of sessions/users)
- Combined multiple journey layers using `pd.concat()`  

---

## Tools & Technologies

- Python  
- Pandas   
- Plotly (Sankey visualization)  
- Jupyter Notebook  

---

## Key Techniques

- Session-based grouping to reconstruct user journeys  
- Timestamp sorting to ensure correct navigation sequence  
- Groupby aggregation to measure page-to-page transitions  
- Concatenation of multiple flow layers  
- Sankey diagram modeling for flow visualization  

---

## Results

- Identified dominant user flows such as:
  - Google → Home → Product → Checkout  
  - Facebook → Landing Page → Exit  

- Observed variation in journey patterns by traffic source  
- Highlighted high-performing conversion paths  

---

## Insights & Recommendations

- Optimize high drop-off pages to improve retention  
- Strengthen internal linking from landing pages to product pages  
- Focus marketing investment on high-conversion traffic sources  
- Simplify early-stage navigation to reduce friction  
- Personalize landing pages based on acquisition source behavior  

---

## Expected Impact

- Improve conversion rate across the funnel  
- Reduce user drop-off in mid-funnel stages  
- Increase session depth and engagement  
- Optimize marketing ROI through better channel allocation  
- Provide clear visibility into customer journey behavior  
