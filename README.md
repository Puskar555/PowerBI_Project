# 📊 Sales Analytics Dashboard - Power BI

A comprehensive sales analytics solution built with Power BI, featuring customer insights, product performance tracking, and marketing campaign ROI analysis.

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Measures-orange?style=for-the-badge)
![Star Schema](https://img.shields.io/badge/Star_Schema-Data_Model-blue?style=for-the-badge)

---

## 📋 Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Data Model](#data-model)
- [Key Metrics](#key-metrics)
- [Dashboard Pages](#dashboard-pages)
- [Technologies Used](#technologies-used)
- [How to Use](#how-to-use)
- [Project Structure](#project-structure)

---

## 🎯 Overview

This Power BI project analyzes sales performance across multiple dimensions including products, customers, marketing campaigns, and sales channels. The dashboard provides actionable insights for business decision-making through interactive visualizations and KPI tracking.

**Key Capabilities:**
- 📈 Revenue and profitability analysis
- 👥 Customer segmentation and retention tracking
- 🎯 Marketing campaign ROI measurement
- 📦 Product performance evaluation
- 🌍 Geographic sales distribution
- ⏱️ Time-based trend analysis

---

## ✨ Features

### Interactive Dashboards
- **6 report pages** with 97+ interactive visuals
- **Dynamic slicers** for multi-dimensional filtering
- **Drill-through capabilities** for detailed analysis
- **Tooltip pages** for enhanced user experience
- **Field parameters** for flexible visualization

### Advanced Analytics
- Return rate tracking with net metrics
- Customer lifetime value analysis
- Campaign attribution modeling
- Loyalty tier performance comparison
- Channel effectiveness measurement

### Data Quality
- Star schema design for optimal performance
- 19 custom DAX measures
- Proper fact/dimension separation
- Time intelligence enabled

---

## 🗄️ Data Model

### Architecture: Star Schema

```
                    DimProducts          DimCustomers         DimDate
                   ┌───────────┐        ┌────────────┐      ┌─────────┐
                   │ Brand     │        │ CustomerID │      │ Year    │
                   │ Category  │        │ Country    │      │ Month   │
                   │ Product   │        │ Loyalty    │      │ Date    │
                   └─────┬─────┘        └──────┬─────┘      └────┬────┘
                         │                     │                 │
                         └─────────────────────┼─────────────────┘
                                              │
                                    ┌─────────▼─────────┐
                                    │   Sales (Fact)    │
                                    ├───────────────────┤
                                    │ • Revenue         │
                                    │ • Quantity        │
                                    │ • Cost            │
                                    │ • Returns         │
                                    └───────────────────┘
                                              ▲
                         ┌────────────────────┼────────────────────┐
                         │                    │                    │
                  ┌──────┴──────┐      ┌──────┴──────┐     ┌──────┴──────┐
                  │DimCampaigns │      │ DimChannel  │     │WebsiteTraffic│
                  └─────────────┘      └─────────────┘     └─────────────┘
```

### Tables

**Fact Table:**
- `Sales-2` - Transaction-level sales data

**Dimension Tables:**
- `DimProducts` - Product hierarchy (Category → Subcategory → Brand → Product)
- `DimCustomers` - Customer demographics and segmentation
- `DimDate` - Calendar table for time intelligence
- `DimCampaigns` - Marketing campaign metadata
- `DimChannel` - Sales channel reference
- `WebsiteTraffic` - Web analytics data
- `ChooseDimension` - Parameter table for dynamic visuals

---

## 📊 Key Metrics (DAX Measures)

### Revenue Metrics
```dax
Total Revenue          # Sum of all sales
Net Kept Revenue       # Revenue after returns
Gross Profit          # Revenue - Cost
Net Gross Profit      # Gross Profit after returns
```

### Customer Metrics
```dax
Total Customers        # Unique customer count
Kept Customers        # Customers who didn't return
Customer Return Rate  # % of returning customers
Revenue per Customer  # Average revenue per customer
```

### Order Metrics
```dax
Orders                # Total order count
Net Orders            # Orders after returns
AOV                   # Average Order Value
Net AOV               # AOV after returns
Net Quantity          # Quantity sold minus returns
```

### Campaign Metrics
```dax
Campaign Revenue      # Revenue attributed to campaigns
Campaign Orders       # Orders from campaigns
Campaign Customers    # Customers acquired via campaigns
Campaign Gross Profit # Profit from campaigns
Campaign AOV          # AOV for campaign orders
```

---

## 📑 Dashboard Pages

### 1. **Overview** (20 visuals)
- Executive summary with key KPIs
- Trend analysis table
- Multi-dimensional slicers (Product, Customer, Location)

### 2. **Product Performance** (16 visuals)
- Product category analysis
- Brand comparison
- Net revenue tracking
- Product hierarchy drill-down

### 3. **Customer Insights** (16 visuals)
- Customer segmentation by loyalty tier
- Geographic distribution
- Gender and demographic analysis
- Retention metrics

### 4. **Marketing Performance** (18 visuals)
- Campaign effectiveness dashboard
- Channel ROI analysis
- Campaign timeline visualization

### 5. **Campaign Details** (11 visuals)
- Detailed campaign metrics
- Multi-row card displays
- Campaign-specific KPIs

### 6. **Product Tooltip** (3 visuals)
- Drill-through tooltip page
- Quick product insights
- Trend sparklines

---

## 🛠️ Technologies Used

- **Power BI Desktop** - Report development
- **DAX** - Calculated measures and columns
- **Power Query (M)** - Data transformation
- **Star Schema** - Data modeling pattern

---

## 🚀 How to Use

### Prerequisites
- Power BI Desktop (latest version recommended)
- Windows 10/11 or Power BI Service access

### Installation Steps

1. **Clone this repository**
   ```bash
   git clone https://github.com/YOUR-USERNAME/powerbi-sales-analysis.git
   cd powerbi-sales-analysis
   ```

2. **Open the Power BI file**
   - Launch Power BI Desktop
   - Open `FINAL_EXAM_5.pbix`

3. **Explore the dashboard**
   - Navigate through the 6 report pages
   - Use slicers to filter data
   - Hover over visuals for tooltips
   - Click on data points for drill-through

### Data Refresh
- Data model uses imported data (no live connection required)
- To update with new data, replace source files and refresh in Power Query

---

## 📁 Project Structure

```
powerbi-sales-analysis/
│
├── README.md                      # This file
├── FINAL_EXAM_5.pbix             # Power BI report file
│
├── documentation/
│   ├── data-model.md             # Detailed data model documentation
│   ├── measures-guide.md         # DAX measures explained
│   └── model-diagram.txt         # ASCII diagram of data model
│
├── images/
│   └── screenshots/              # Dashboard screenshots (add your own)
│       ├── overview.png
│       ├── product-performance.png
│       └── customer-insights.png
│
└── .gitignore                    # Git ignore file
```

---

## 📸 Screenshots

> **Note:** Add screenshots of your dashboards to `images/screenshots/` folder

<!-- Uncomment and add your screenshots
![Overview Dashboard](images/screenshots/overview.png)
*Overview page showing key metrics and trends*

![Product Performance](images/screenshots/product-performance.png)
*Product analysis with category breakdown*
-->

---

## 🎓 Learning Outcomes

This project demonstrates:
- ✅ Star schema data modeling
- ✅ DAX measure development (19 measures)
- ✅ Time intelligence implementation
- ✅ Customer analytics and segmentation
- ✅ Campaign attribution modeling
- ✅ Multi-page report design
- ✅ Interactive slicer configuration
- ✅ Tooltip page implementation
- ✅ Field parameter usage

---

## 📈 Key Insights Delivered

1. **Product Analysis**: Identify top-performing products, categories, and brands
2. **Customer Behavior**: Understand purchase patterns and loyalty impact
3. **Return Analysis**: Track return rates and net revenue impact
4. **Campaign ROI**: Measure marketing effectiveness by channel
5. **Geographic Trends**: Analyze sales distribution by location
6. **Time Analysis**: Identify seasonal patterns and growth trends

---

## 🤝 Contributing

Suggestions and improvements are welcome! Please feel free to:
- Open an issue for bugs or feature requests
- Submit pull requests with enhancements
- Share feedback on the dashboard design

---

## 📝 License

This project is available for educational and portfolio purposes.

---

## 👤 Author

**Your Name**
  - GitHub: [[@visit_on](https://github.com/Puskar555/PowerBI_Project/edit/main)]
- LinkedIn: [LinkedIn](www.linkedin.com/in/puskar-raj-acharya)

---

## 🙏 Acknowledgments

- Data model follows Kimball dimensional modeling methodology
- DAX patterns based on SQLBI best practices
- Dashboard design inspired by modern BI principles

---

**⭐ If you found this project helpful, please give it a star!**
