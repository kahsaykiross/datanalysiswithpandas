# datanalysiswithpandas
plp assignment 
import pandas as pd
import matplotlib.pyplot as plt

# Sample data: sales records
data = {
    'Product': ['Laptop', 'Mouse', 'Laptop', 'Keyboard', 'Mouse', 'Keyboard', 'Laptop'],
    'Quantity Sold': [5, 15, 3, 8, 7, 2, 6],
    'Revenue': [5000, 300, 3000, 800, 140, 200, 6000]
}

# Create DataFrame
df = pd.DataFrame(data)

# Group by Product and calculate total quantity sold and total revenue
summary = df.groupby('Product').agg({
    'Quantity Sold': 'sum',
    'Revenue': 'sum'
}).reset_index()

print("Summary:\n", summary)

# Plot total quantity sold by product
plt.bar(summary['Product'], summary['Quantity Sold'], color='skyblue')
plt.title('Total Quantity Sold by Product')
plt.xlabel('Product')
plt.ylabel('Quantity Sold')
plt.show()
