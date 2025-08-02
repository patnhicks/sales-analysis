# 🛍️ Retail Sales Analysis

This project analyzes retail sales data by department, region, and product, and evaluates regional performance against a sales threshold. The analysis uses `pandas` to generate group-based summaries and highlights key business insights.

## 📊 Features

- Total sales by **Department**
- Average sales by **Region**
- Max sales by **Product**
- Hierarchical grouping:
  - Sales by **Region + Department**
  - Sales by **Region + Store**
- Identifies **high-performing regions** exceeding a given threshold

## 📂 Input

Requires a CSV file with the following columns:

Region, Department, Product, StoreID, SalesAmount


## 🚀 How to Run

1. Make sure `pandas` is installed:
   ```bash
   pip install pandas

2. Update the path to your CSV file in the script:

sales = pd.read_csv(r"path_to_your_csv_file.csv")

3. Run the script:

python sales_analysis.py

📈 Example Output
Total Sales by Department:
Electronics      42000.0
Clothing         31000.0
...

Highest Sales by Product:
TV               9000.0
Laptop           8500.0
...

Highest Performing Region:
East             18000.0

🛠 Tech Stack

    Python

    pandas