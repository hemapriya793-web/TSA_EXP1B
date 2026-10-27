# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:

```
```python
from matplotlib import pyplot as plt
import pandas as pd

df = pd.read_csv("/content/superstore_final_dataset.csv", encoding="latin1")

print(df.head())

# Convert Order Date to datetime
df['Order Date'] = pd.to_datetime(df['Order Date'])

# Extract year
df['Year'] = df['Order Date'].dt.year

# Calculate total sales for each year
yearly_sales = df.groupby('Year')['Sales'].sum()

# Plot graph
plt.figure(figsize=(10, 6))
plt.plot(yearly_sales.index, yearly_sales.values, label='Total Sales', color='black')

plt.title('Time Series Plot of Sales Each Year')
plt.xlabel('Year')
plt.ylabel('Total Sales')
plt.legend()
plt.grid(True)

plt.show()
```


## output:
<img width="762" height="560" alt="Screenshot 2026-10-17 091919" src="https://github.com/user-attachments/assets/e63376f9-eab7-4734-98d9-a97d92dd6090" />




### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
