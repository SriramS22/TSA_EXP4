# Ex.No:04   FIT ARMA MODEL FOR TIME SERIES
### Date: 12.11.2024
### Name : Sriram S
### Reg No : 212222240105
### AIM:
To implement ARMA model in python.
### ALGORITHM:
1. Import necessary libraries.
2. Set up matplotlib settings for figure size.
3. Define an ARMA(1,1) process with coefficients ar1 and ma1, and generate a sample of 1000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

4. Display the autocorrelation and partial autocorrelation plots for the ARMA(1,1) process using
plot_acf and plot_pacf.
5. Define an ARMA(2,2) process with coefficients ar2 and ma2, and generate a sample of 10000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

6. Display the autocorrelation and partial autocorrelation plots for the ARMA(2,2) process using
plot_acf and plot_pacf.
### PROGRAM:
```
import pandas as pd
from statsmodels.tsa.arima.model import ARIMA
import matplotlib.pyplot as plt

# Load dataset (replace 'your_data.csv' with the actual filename after uploading the dataset)
data = pd.read_csv('/content/mulgrave.csv', parse_dates=['Timestamp'], index_col='Timestamp')

# Selecting the "Q" column and dropping NaN values
data_q = data['Q'].dropna()

# Fit ARMA model (ARMA is a specific case of ARIMA with no differencing, so use ARIMA with order=(p, 0, q))
p = 1  # Order of the autoregressive part
q = 1  # Order of the moving average part
model = ARIMA(data_q, order=(p, 0, q))
arma_result = model.fit()

# Print the model summary
print(arma_result.summary())

# Plotting the original data and the fitted values
plt.figure(figsize=(10, 6))
plt.plot(data_q, label='Original')
plt.plot(arma_result.fittedvalues, color='red', label='Fitted')
plt.title('ARMA Model Fit')
plt.legend()
plt.show()
```
### Output:

![download (1)](https://github.com/user-attachments/assets/49a9e7e0-7ff2-4395-9438-03db81990fa7)

### RESULT:
Thus, a python program is created to fir ARMA Model successfully.
