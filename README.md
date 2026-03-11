# Pricing-Strategy-Demand-Elasticity-Analysis
Analyze how product price changes affect consumer demand and determine pricing strategies that maximize revenue.

# Data profiling for SampleSuperstore
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df = pd.read_csv("SampleSuperstore.csv")
df.head()
df.info()
df.describe()

# Defines discount, final price, and total revenue 
dataK = pd.read_csv("SampleSuperstore.csv")
dataK["Discount"] = dataK["Discount"].astype(float)
dataK["Final_Price"] = dataK["Sales"] / dataK["Quantity"]
dataK["Total_Revenue"] = dataK["Sales"]

# Shows relationship between price and quantity 
sns.scatterplot(x="Final_Price", y="Quantity", data=dataK)
plt.show()

plt.figure(figsize=(10,6))
# ci=95 adds error bars. If the bar at 13 has a very long vertical line,
# it means the data for '13' is inconsistent or has very few rows.
sns.barplot(x="Quantity", y="Final_Price", data=dataK, ci=95, palette="magma")

plt.title("Average Unit Price by Quantity (with Confidence Intervals)")
plt.show()
