# 🛒 Walmart Retail Data Pipeline

This project implements a **data pipeline** to analyze Walmart’s sales data around **public holidays** such as Thanksgiving, Christmas, and the Super Bowl.  
The pipeline extracts, transforms, and loads sales and complementary data, enabling insights into **supply and demand patterns** across different months.

---

## 📌 Project Overview

Walmart is the largest retail store in the U.S., with contributing over **$80 billion (13% of sales) by the end of 2022**.  
Holidays significantly affect demand, and this project helps analyze their impact using a structured pipeline.

The pipeline performs:
1. **Extract**  
   - Loads sales data from PostgreSQL (`grocery_sales` table).  
   - Reads complementary data from `extra_data.parquet`.  
   - Merges them into a single dataset.  

2. **Transform**  
   - Cleans missing values using column means.  
   - Filters weekly sales above **10,000 USD**.  
   - Converts dates to months.  
   - Keeps only relevant columns.  

3. **Aggregate**  
   - Computes **average monthly sales** across all stores.  

4. **Load**  
   - Saves the cleaned dataset (`clean_data.csv`).  
   - Saves the aggregated dataset (`agg_data.csv`).  

5. **Validate**  
   - Ensures the generated CSV files exist.

---

## 📂 Data Sources

### 🛍 Grocery Sales (`grocery_sales` - PostgreSQL)
| Column        | Description |
|---------------|-------------|
| index         | Unique row ID |
| Store_ID      | Store number |
| Date          | Week of sales |
| Weekly_Sales  | Sales for the given store |

### 📊 Complementary Data (`extra_data.parquet`)
| Column        | Description |
|---------------|-------------|
| IsHoliday     | 1 if the week includes a holiday, else 0 |
| Temperature   | Temperature during sales week |
| Fuel_Price    | Fuel price in the region |
| CPI           | Consumer Price Index |
| Unemployment  | Unemployment rate |
| MarkDown1-4   | Promotional markdowns |
| Dept          | Department number |
| Size          | Store size |
| Type          | Store type |

---

## 🛠️ Tech Stack

- **Python 3.x**  
- **Pandas** (data processing)  
- **PostgreSQL** (sales database)  

---

## ⚙️ How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/walmartecomm.git
   cd walmartecomm
