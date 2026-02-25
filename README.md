# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 25.02.2026
### Name: Ramesh Renuka
### Reg.no: 212223240136

### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.
### Software Required:
Google Colab
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose
data = pd.read_csv('/content/retail_sales_dataset.csv', parse_dates=['Date'], index_col='Date')
data.head()
decomposition = seasonal_decompose(data['Total Amount'], model='additive', period=7)
# Plot the decomposition
plt.figure(figsize=(10, 12)) # Adjust the figure size for a square shape
# Original Data
plt.subplot(411)
plt.plot(data['Total Amount'], label='Total Amount')
plt.legend(loc='upper left')
plt.title('Retail Sales (Total Amount)')
# Trend Plot
plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Linear Trend Plot')
# Seasonal Plot
plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality Plot')
# Residual Plot
plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual Plot')

plt.tight_layout()
plt.show()
```
### OUTPUT:
FIRST FIVE ROWS:
<img width="940" height="239" alt="image" src="https://github.com/user-attachments/assets/6b723881-b9a0-4ae4-a19d-819bc92312a0" />

PLOTTING THE DATA:
<img width="671" height="182" alt="image" src="https://github.com/user-attachments/assets/2f11e2ea-5a4e-4804-9ded-2b643ccc6ab5" />

SEASONAL PLOT REPRESENTATION :
<img width="628" height="191" alt="image" src="https://github.com/user-attachments/assets/92b853f8-d85a-4b68-b10b-b6475f464f6e" />

TREND PLOT REPRESENTATION :
<img width="634" height="185" alt="image" src="https://github.com/user-attachments/assets/e79ce0da-bde8-494f-858d-5feef3f7907e" />

OVERAL REPRESENTATION:
<img width="674" height="154" alt="image" src="https://github.com/user-attachments/assets/efba4271-9c49-4269-9b9a-3b5e3b7423de" />



### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
