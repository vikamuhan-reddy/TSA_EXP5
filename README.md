# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 11/05/2026


### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.


### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.
   

### PROGRAM:
```py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

data = pd.read_csv('/content/AirPassengers.csv',parse_dates=['Month'],index_col='Month')

decomposition = seasonal_decompose(data['#Passengers'], model='additive',period=12)

plt.figure(figsize=(10, 12))  # Adjust the figure size for a square shape

plt.subplot(411)
plt.plot(data['#Passengers'], label='Monthly Passengers')
plt.legend(loc='upper left')
plt.title('Monthly Passengers')

plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Linear Trend Plot')

plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality Plot')

plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual Plot')
plt.tight_layout()
plt.show()
```


### OUTPUT:

<img width="797" height="227" alt="Screen Shot 2026-05-11 at 08 42 00" src="https://github.com/user-attachments/assets/7494e9a8-c8d7-4e5a-be60-d5176998b56d" />

<img width="797" height="227" alt="Screen Shot 2026-05-11 at 08 42 38" src="https://github.com/user-attachments/assets/cb1f9dea-730b-4df8-ba2e-2284a8963d35" />

<img width="797" height="227" alt="Screen Shot 2026-05-11 at 08 43 00" src="https://github.com/user-attachments/assets/dfcc497f-e7f1-41c7-8783-fe07d30fbe3a" />'

<img width="797" height="227" alt="Screen Shot 2026-05-11 at 08 46 58" src="https://github.com/user-attachments/assets/2329d03f-ddbf-4e17-acc6-cee5b82b6d0d" />



### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
