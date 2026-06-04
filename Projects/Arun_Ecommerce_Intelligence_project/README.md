# End-to-End E-commerce Intelligence System
## Building a Customer 360 Analytics Framework

A complete data analytics project simulating a real-world e-commerce business intelligence scenario. The project integrates multiple data sources, builds a unified Customer 360 view, and generates actionable business insights from raw data.

---

## Project Structure

```
Arun_Ecommerce_Intelligence_Project/
│
├── README.md
├── ecommerce_intelligence_project.ipynb
│
├── dataset/
│   ├── customers.csv
│   ├── orders.csv
│   ├── order_item.csv
│   ├── payments.csv
│   ├── reviews.csv
│   ├── products.csv
│   ├── sellers.csv
│   ├── location.csv
│   └── category_translation.csv
│
└── plots/
    ├── plot_01_monthly_revenue.png
    ├── plot_02_monthly_orders.png
    ├── plot_03_top_categories.png
    ├── plot_04_customer_segments.png
    ├── plot_05_review_scores.png
    ├── plot_06_delivery_time.png
    ├── plot_07_delivery_vs_review.png
    ├── plot_08_correlation_heatmap.png
    ├── plot_09_top_states.png
    ├── plot_10_payment_types.png
    └── plot_11_clv_distribution.png
```

---

## Dataset Overview

The project uses a multi-table relational e-commerce dataset:

| File | Description |
|---|---|
| `customers.csv` | Customer demographic and location information |
| `orders.csv` | Central order lifecycle table (purchase, delivery timestamps) |
| `order_item.csv` | Product-level details for each order |
| `payments.csv` | Payment type and value per order |
| `reviews.csv` | Customer review scores and comments |
| `products.csv` | Product details and categories |
| `sellers.csv` | Seller information |
| `location.csv` | Geographic information |
| `category_translation.csv` | Product category names translated to English |

---

## Project Workflow

### Step 1: Data Loading and Initial Exploration
- Load all 9 datasets using Pandas
- Inspect structure, data types, null counts
- Identify primary and foreign key relationships

### Step 2: Data Cleaning and Preprocessing
- Convert date columns to datetime format
- Standardize column names (lowercase, strip spaces)
- Remove duplicate records
- Handle missing values appropriately

### Step 3: Data Integration
Merge all tables into a single Master Dataset in this sequence:

```
orders + customers
      + order_items
      + products + category_translation
      + sellers
      + payments
      + reviews
```

### Step 4: Feature Engineering
New features created:
- `delivery_time_days` — days from purchase to delivery
- `delivery_delay_days` — actual vs estimated delivery difference
- `item_total_value` — price + freight per item
- `total_order_value` — total value per order
- `num_items` — number of items per order
- `purchase_frequency` — how many orders per customer
- `total_lifetime_value` — total spend per customer (CLV)
- `customer_segment` — Low / Mid / High Value
- `customer_type` — New vs Repeat

### Step 5: Exploratory Data Analysis (EDA)
- **Customer Analysis** — New vs Repeat, Value Segments, Geographic distribution
- **Revenue Analysis** — Monthly trends, Order volume, Payment types
- **Product Analysis** — Top categories by revenue and order count
- **Seller Analysis** — Top sellers, Revenue concentration
- **Review Analysis** — Score distribution, Delivery time vs satisfaction

### Step 6: Data Visualization
11 charts created using Matplotlib and Seaborn:
- Monthly revenue and order volume trends
- Top product categories by revenue
- Customer value segments and New vs Repeat pie chart
- Review score distribution
- Delivery time histogram
- Delivery time vs review score box plot
- Correlation heatmap
- Top states by customer count
- Payment type distribution
- Customer Lifetime Value distribution

### Step 7: Business Insights and Recommendations
Six data-backed insights covering:
1. Revenue concentration in top product categories
2. Low customer retention rate
3. Delivery time impact on review scores
4. Seller concentration risk
5. Geographic market opportunities
6. Payment method distribution

---

## Key Findings

| Metric | Value |
|---|---|
| Avg Delivery Time | ~12 days |
| Avg Review Score | 4.0 / 5 |
| Repeat Customer Rate | ~3% |
| Dominant Payment Method | Credit Card |
| Top Revenue Category | Health & Beauty |

---

## Technologies Used

| Tool | Purpose |
|---|---|
| Python 3 | Programming language |
| Pandas | Data loading, cleaning, merging |
| NumPy | Numerical operations |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualizations |
| Jupyter Notebook | Interactive development |

---

## How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/Arun_Ecommerce_Intelligence_Project.git
   ```

2. Install required libraries:
   ```bash
   pip install pandas numpy matplotlib seaborn
   ```

3. Open the notebook:
   ```bash
   jupyter notebook ecommerce_intelligence_project.ipynb
   ```

4. Run all cells top to bottom (**Kernel > Restart & Run All**)

---

## Author

**Arun Singh**
Data Analytics Project
