# 🛒 E-Mart Sales Analytics — Power BI Dashboard

A comprehensive **Power BI business intelligence dashboard** for E-Mart, a multi-category retail store. This project transforms raw sales data into actionable insights across products, promotions, customers, and geographies.

---

## 📸 Dashboard Pages

| Page | Description |
|------|-------------|
| **Overview** | High-level KPIs, sales trends over time, profit vs. sales relationship, and city-level sales map |
| **Top/Bottom 5 Analysis** | Best and worst performing products by Sales, Profit, and Quantity Sold |
| **Comparison — Sales / Profit / Quantity** | Side-by-side comparison of two user-selected time periods |
| **Total Visual** | Granular order-level table with advanced visual filters |

---

## 📦 Product Categories

The dashboard covers sales across **8 product categories**:

- 🖥️ Electronics
- 👟 Footwear
- 👗 Clothing
- 🏠 Home Appliances
- 💍 Accessories
- 🍳 Kitchenware
- 👜 Bags
- 🧴 Personal Care

---

## 📊 Key Features & Analytics

### 1. 🏆 Top / Bottom 5 Product Analysis
Bar charts highlighting the best and worst performing products across three dimensions:
- Top 5 & Bottom 5 by **Sales**
- Top 5 & Bottom 5 by **Profit**
- Top 5 & Bottom 5 by **Quantity Sold**

### 2. 📈 Sales Trends Over Time
A line chart (with smooth curves) showing **Net Sales over time**, with drill-down support across:
- Daily → Monthly → Quarterly → Annually

### 3. 🔵 Profit vs. Net Sales Relationship
A scatter chart visualizing the **correlation between Profit and Net Sales** across products and periods.

### 4. ⚖️ Period Comparison
Clustered column charts enabling users to **compare any two time periods** for:
- Total Sales
- Total Profit
- Total Quantity Sold

### 5. 🏷️ Discount Analysis
Bar charts showing the **average discount offered per Promotion Category**, powered by the `Dim Promotion` table.

### 6. 🔢 Total Orders KPI
A **card visual** displaying the total count of orders placed.

### 7. 📋 Order-Level Detail Table
A fully filterable table with per-order breakdown including:
- Sales, Profit, Discount, Net Sales, Discount Percentage
- Price Per Unit (INR), Units Sold
- Customer ID, Order ID, Product ID, Promotion ID

**Available Slicers / Visual Filters:**
- 📦 Product Name
- 📅 Date
- 👤 Customer ID
- 🎟️ Promotion Categories

### 8. 🗺️ Sales by City
An interactive **map visual** plotting sales performance across different cities using `Dim Customers.City`.

---

## 🗃️ Data Model

The project uses a **star schema** with the following tables:

### Fact Table
| Field | Description |
|-------|-------------|
| `Order ID` | Unique order identifier |
| `Product ID` | Product reference key |
| `CustomerID` | Customer reference key |
| `PromotionID` | Promotion reference key |
| `Date (dd/mm/yyyy)` | Order date |
| `Units Sold` | Quantity of units sold |
| `Price Per Unit (INR)` | Unit price in Indian Rupees |
| `Discount` | Discount amount applied |
| `Discount Percentage` | Discount as a percentage |
| `Net Sales` | Revenue after discount |
| `Total Sales` | Gross sales value |
| `Profit` | Net profit per order |

### Dimension Tables
| Table | Key Fields |
|-------|-----------|
| `Dim Product` | Product Name, Category |
| `Dim Customers` | Customer Name, City |
| `Dim Promotion` | Promotion Name / Category |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| **Microsoft Power BI Desktop** | Dashboard development & publishing |
| **Power Query (M)** | Data transformation & cleaning |
| **DAX** | Calculated measures and KPIs |
| **Excel / CSV** | Source data |

---

## 🚀 Getting Started

### Prerequisites
- [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free download)

### Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/e-mart-powerbi.git
   cd e-mart-powerbi
   ```

2. **Open the report**
   - Launch **Power BI Desktop**
   - Open `Power_BI_Project__E-Mart_.pbix`

3. **Connect your data source** *(if needed)*
   - Go to **Home → Transform Data → Data Source Settings**
   - Update the file path to point to your local data files

4. **Refresh the data**
   - Click **Home → Refresh** to load the latest data

---

## 📁 Project Structure

```
e-mart-powerbi/
│
├── Power_BI_Project__E-Mart_.pbix   # Main Power BI report file
├── E-Mart_Requirements.pptx         # Project requirements document
├── data/                            # Source data files (CSV/Excel)
│   └── Store+Data.xlsx
└── README.md                        # Project documentation
```

---

## 📌 DAX Measures (Key)

```dax
-- Example measures used in the dashboard
Total Sales = SUM('Fact Table'[Total Sales])
Total Profit = SUM('Fact Table'[Profit])
Total Net Sales = SUM('Fact Table'[Net Sales])
Total Orders = DISTINCTCOUNT('Fact Table'[Order ID])
Avg Discount % = AVERAGE('Fact Table'[Discount Percentage])
```

---
