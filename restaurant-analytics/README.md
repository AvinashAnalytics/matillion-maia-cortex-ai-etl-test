# 🍽️ Restaurant Analytics Platform

## Project Overview

A comprehensive **end-to-end data analytics platform** for restaurant business intelligence, built using **Matillion Data Productivity Cloud**. This project demonstrates advanced data engineering patterns, automated pipeline orchestration, and executive-level business intelligence.

### 🎯 Business Impact
- **Customer Lifetime Value (CLV)** analysis for targeted marketing
- **Average Order Value (AOV)** optimization strategies  
- **Menu performance** insights for inventory management
- **Employee performance** metrics for operational excellence
- **Executive dashboards** for strategic decision making

---

## 📁 Project Structure

```
restaurant-analytics/
├── orchestration/
│   └── data-ingestion.orch.yaml     # Main data pipeline orchestrator
├── transformation/
│   ├── file-registry.tran.yaml      # File mapping and registry
│   ├── business-analytics.tran.yaml # Core KPI calculations
│   └── executive-dashboard.tran.yaml # Executive summary dashboards
├── docs/
│   └── maia-ai-prompts.md           # Complete Maia AI implementation guide
└── README.md                         # This comprehensive guide
```

---

## 🚀 Quick Start with Maia AI

### Prerequisites
- Access to **Matillion Data Productivity Cloud**
- **Snowflake** data warehouse connection
- **Restaurant CSV files** in Snowflake stage: `mat_pro.resturant/`
  - `rest_menus.csv`
  - `rest_orders.csv` 
  - `rest_customers.csv`
  - `rest_employees.csv`

### ⚡ One-Command Implementation

Simply ask **Maia AI**:

> "Create the complete restaurant analytics platform using the files in the restaurant-analytics folder. Run the data ingestion pipeline first, then execute the business analytics and executive dashboard transformations."

**That's it!** Maia will handle everything automatically.

---

## 🔧 Manual Implementation Guide

If you prefer step-by-step control, follow these **exact Maia AI prompts**:

### Step 1: Project Setup
```
"Create a new project folder called 'restaurant-analytics' with subfolders for 'orchestration' and 'transformation'."
```

### Step 2: Data Ingestion Pipeline
```
"Create an orchestration pipeline called 'data-ingestion.orch.yaml' that:
1. Uses a file registry to map restaurant CSV files to table names
2. Iterates through each file using table-iterator
3. Creates tables dynamically using SQL executor with schema inference
4. Loads data with error handling
5. Runs business analytics transformation
6. Runs executive dashboard transformation

Use these variables:
- stage_name: 'mat_pro.resturant'
- file_format: 'mat_pro.infer_fmt'
"
```

### Step 3: File Registry
```
"Create a transformation pipeline 'file-registry.tran.yaml' with a fixed-flow component that maps:
- rest_menus.csv → REST_MENUS
- rest_orders.csv → REST_ORDER  
- rest_customers.csv → REST_CUSTOMERS
- rest_employees.csv → REST_EMPLOYEES

Output to table 'file_list' with columns: file_name, table_name, file_type."
```

### Step 4: Business Analytics
```
"Create 'business-analytics.tran.yaml' that:
1. Joins all 4 restaurant tables (customers, employees, menus, orders)
2. Calculates total_price (price × quantity)
3. Creates these KPI outputs:
   - CLV table (customer lifetime value)
   - AOV table (average order value) 
   - TOP_SELLING table (menu performance)
   - SALES_PERFO table (employee performance)
   - master_rest_table (complete dataset)
"
```

### Step 5: Executive Dashboard
```
"Create 'executive-dashboard.tran.yaml' that:
1. Reads CLV, AOV, and TOP_SELLING tables
2. Creates executive summary with KPI calculations
3. Generates category performance analysis
4. Outputs EXEC_SUMMARY, EXEC_CLV_DATA, and EXEC_CATEGORY_DASHBOARD tables
"
```

---

## 📊 Data Pipeline Architecture

### 🔄 Flow Diagram
```
[CSV Files] → [File Registry] → [Table Iterator] → [Dynamic Table Creator]
     ↓
[Business Analytics] → [5 KPI Tables] → [Executive Dashboard] → [3 Executive Tables]
```

### 📋 Output Tables
| Table Name | Purpose | Key Metrics |
|------------|---------|-------------|
| `CLV` | Customer Lifetime Value | customer_id, customer_name, total_spent |
| `AOV` | Average Order Value | avg_order_value |
| `TOP_SELLING` | Menu Performance | item_name, category, total_revenue |
| `SALES_PERFO` | Employee Performance | employee_name, total_revenue_generated |
| `EXEC_SUMMARY` | Executive KPIs | dashboard_title, report_date, avg_order_value |
| `EXEC_CATEGORY_DASHBOARD` | Category Performance | category, sum_total_revenue, count_item_name |
| `EXEC_CLV_DATA` | CLV Executive Summary | sum_total_spent, count_customer_id, avg_total_spent |

---

## 🎯 Interview Presentation Points

### 💼 Business Value
✅ **Automated Data Ingestion** - Zero-touch file processing  
✅ **Dynamic Schema Inference** - Handles changing data structures  
✅ **Comprehensive Error Handling** - Production-ready reliability  
✅ **Modular Design** - Separation of concerns (orchestration vs transformation)  
✅ **Executive Dashboards** - C-suite ready business intelligence  

### 🔧 Technical Excellence
✅ **Iterator Pattern** - Scalable file processing  
✅ **Variables & Parameters** - Environment flexibility  
✅ **Component Reusability** - DRY principles  
✅ **Data Quality** - Validation and logging  
✅ **Performance Optimization** - Efficient joins and aggregations  

### 📈 Scalability Features
✅ **Add New Files** - Simply update file registry  
✅ **New KPIs** - Extend business analytics pipeline  
✅ **Additional Dashboards** - Clone executive dashboard pattern  
✅ **Multi-Environment** - Variable-driven configuration  

---

## 🛠️ Advanced Customization

### Adding New Data Sources
1. Update `file-registry.tran.yaml` with new file mappings
2. Pipeline automatically processes new files
3. Add transformations to `business-analytics.tran.yaml` as needed

### Creating New KPIs
```
"Add additional KPIs like seasonal trends, customer segmentation, or promotional effectiveness analysis."
```

### Executive Dashboard Extensions
```
"Create additional executive summary tables that show monthly trends and seasonal patterns."
```

---

## 🎉 Success Metrics

After implementation, you'll have:
- ✅ **4 source tables** automatically created and populated with quality validation
- ✅ **8 advanced analytics tables** with comprehensive business KPIs and seasonal analysis
- ✅ **4 executive tables** ready for C-suite dashboard tools
- ✅ **Real-time data quality monitoring** with automated validation flags
- ✅ **Production-grade error handling** with comprehensive logging and recovery
- ✅ **Advanced business intelligence** including retention analysis and seasonal trends

---

*Built with ❤️ using Matillion Data Productivity Cloud and Maia AI*
