# -*- coding: utf-8 -*-
"""
Created on Mon Jul 21 11:20:53 2025
Author: Pat Hicks
Title: Sales analysis
Summary: This project analyzes retail sales data by department, region, and product, and evaluates regional performance against a sales threshold. The analysis uses `pandas` to generate group-based summaries and highlights key business insights.
"""

import pandas as pd


# Sales Summary by Department, Region, and Product
def sales_summary(sales):
    #Sales by dept
    total_sales_dept = sales.groupby('Department')['SalesAmount'].sum().sort_values(ascending=False)
    #Sales by region
    avg_sales_region = sales.groupby('Region')['SalesAmount'].mean().sort_values(ascending=False)
    #Sales by product
    highest_sales_product = sales.groupby('Product')['SalesAmount'].max().sort_values(ascending=False)

    return total_sales_dept, avg_sales_region, highest_sales_product

# Hierarchical Grouping by Region and Store
def grouping_regionDept_and_regionStore(sales):
    #sales by region and dept
    sales_by_regionDept = sales.groupby(['Region', 'Department'])['SalesAmount'].sum()
    #sales by region and storeID
    sales_by_regionStore = sales.groupby(['Region', 'StoreID'])['SalesAmount'].sum()
    # Need to rewrite to keep region and sort by subgroup

    return sales_by_regionDept, sales_by_regionStore

# Regional Performance Evaluation with Threshold

def evaluate_regional_performance(sales, threshold=10000):
    #total sales per region
    total_sales_region = sales.groupby('Region')['SalesAmount'].sum().sort_values(ascending=False)

    #filter based on threshold
    high_performer_region = total_sales_region[total_sales_region >= threshold]
    
    return total_sales_region, high_performer_region

def main():

    #read csv for data
    sales = pd.read_csv(r"C:\\Users\patnh\OneDrive\Desktop\retail_sales.csv")

    #Calling teh functions
    total_sales_dept, avg_sales_region, highest_sales_product = sales_summary(sales)
    sales_by_regionDept, sales_by_regionStore = grouping_regionDept_and_regionStore(sales)
    total_sales_region, high_performer_region = evaluate_regional_performance(sales, threshold=10000)
    
    print("\nTotal Sales by Department:")
    print(total_sales_dept.round(2))
    
    print("\nAverage Sales by Region")
    print(avg_sales_region.round(2))
    
    print("\nHighest Sales by Product")
    print(highest_sales_product)
    
    print("\nSales by Region and Dept")
    print(sales_by_regionDept)
    
    print("\nSales by Region and Store")
    print(sales_by_regionStore)
    
    print("\nTotal Sales by Region - Descending")
    print(total_sales_region)
    
    print("\nHighest Performing Region")
    print(high_performer_region)

# Structuring Your Program with main() 
if __name__ == "__main__":
    main()
