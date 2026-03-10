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
