# Ex.No:04   FIT ARMA MODEL FOR TIME SERIES
# DEVELOPED BY: Sriram S
# REGISTER NO: 212222240105
# Date: 



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
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.arima_process import ArmaProcess
from statsmodels.graphics.tsaplots import plot_acf, plot_pacf
```
# Set up matplotlib settings for figure size
```
plt.rcParams["figure.figsize"] = (12, 6)
```
# Define and generate ARMA(1,1) process
```
ar1 = np.array([1, -0.5])  # AR coefficient: 1 for lag 0, -0.5 for lag 1
ma1 = np.array([1, 0.4])   # MA coefficient: 1 for lag 0, 0.4 for lag 1
arma_11_process = ArmaProcess(ar1, ma1)
```
# Generate 1000 data points from ARMA(1,1)
```
np.random.seed(42)
sample_arma_11 = arma_11_process.generate_sample(nsample=1000)
```
# Plot the time series of ARMA(1,1)
```
plt.figure()
plt.plot(sample_arma_11)
plt.title("ARMA(1,1) Time Series")
plt.xlim([0, 1000])
plt.show()
```
# Display the autocorrelation and partial autocorrelation plots for ARMA(1,1)
```
plot_acf(sample_arma_11, lags=40)
plt.title("ACF for ARMA(1,1)")
plt.show()

plot_pacf(sample_arma_11, lags=40)
plt.title("PACF for ARMA(1,1)")
plt.show()
```
# Define and generate ARMA(2,2) process
```
ar2 = np.array([1, -0.3, 0.5])  # AR coefficients: 1 for lag 0, -0.3 for lag 1, 0.5 for lag 2
ma2 = np.array([1, 0.2, -0.3])  # MA coefficients: 1 for lag 0, 0.2 for lag 1, -0.3 for lag 2
arma_22_process = ArmaProcess(ar2, ma2)
```
# Generate 10000 data points from ARMA(2,2)
```
np.random.seed(42)
sample_arma_22 = arma_22_process.generate_sample(nsample=10000)
``` 
# Plot the time series of ARMA(2,2)
```
plt.figure()
plt.plot(sample_arma_22)
plt.title("ARMA(2,2) Time Series")
plt.xlim([0, 10000])
plt.show()
```
# Display the autocorrelation and partial autocorrelation plots for ARMA(2,2)
```
plot_acf(sample_arma_22, lags=40)
plt.title("ACF for ARMA(2,2)")
plt.show()

plot_pacf(sample_arma_22, lags=40)
plt.title("PACF for ARMA(2,2)")
plt.show()
```

# OUTPUT:
# SIMULATED ARMA(1,1) PROCESS:
![image](https://github.com/user-attachments/assets/a48dc42e-43d9-424d-9eac-c913859c40f2)


# ACF for ARMA(1,1):
![image](https://github.com/user-attachments/assets/713c0ce5-51c0-4efc-a0e6-ecf3b0a3cca4)


# PACF for ARMA(1,1):
![image](https://github.com/user-attachments/assets/fa0d74d0-124a-4d90-b19d-1711d0d119f0)


# SIMULATED ARMA(2,2) PROCESS:
![image](https://github.com/user-attachments/assets/bbf324c6-1126-4ebc-a41d-d99fd32999e7)


# ACF for ARMA(2,2):
![image](https://github.com/user-attachments/assets/f900780f-6444-40fc-99fa-971f938d9ffe)
# PACF for ARMA(2,2):
![image](https://github.com/user-attachments/assets/01a34c45-d8bd-4f7c-b74c-e6587afe3fa1)



# RESULT:
Thus the program was successfully created to fit ARMA model for Time series for airline complaints dataset.
