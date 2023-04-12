# Meteorological-data-analysis-and-forecasting

<h2>Abstract</h2>
<br>
This project aims to show how the Autoregressive Integrated Moving Average (ARIMA) model can be used to analyse meteorological data and forecast future weather patterns. The project is based on an examination of historical weather data from a certain place over a specific time period.
The project starts with a brief overview of ARIMA and its application in time series forecasting. Following that is a full review of the meteorological data used in the study. Temperature, humidity, wind speed, and precipitation data were collected over a number of years. The project then moves on to the data preprocessing procedure, which entails cleaning, normalizing, and converting the data so that it is ready for analysis. The ARIMA model is then applied to the preprocessed data to determine the model parameters that best fit the data. To pick the best ARIMA model, the study applies a variety of statistical approaches, including the Akaike Information Criterion (AIC) and the Bayesian Information Criterion (BIC).
The results of the ARIMA model are shown in the following section. The study assesses the ARIMA model's performance using metrics such as Mean Absolute Error (MAE), Mean Absolute Percentage Error (MAPE), and Root Mean Squared Error (RMSE). The results show that the ARIMA model is quite good at forecasting meteorological data.
Furthermore, the project also investigates the effect of exogenous variables such as seasonal variations, extreme weather occurrences, and climatic changes on the forecasting accuracy of the ARIMA model. According to the study, incorporating these elements considerably enhances the accuracy of the ARIMA model.
In conclusion, this project aims to provides useful insights into the use of ARIMA in meteorological data analysis and forecasting. The project confirms the ARIMA model's accuracy in predicting weather patterns, particularly when exogenous variables are included. The project findings could also be used for weather forecasting and disaster preparedness.
<br>

<h2>Models Information</h2>
<br>
To analyse and visualise the data, this project puts a meteorological dataset into a Pandas dataframe. The models and libraries used in the script are listed below:
<ul>
<li>
Pandas: Pandas is a well-known Python data manipulation toolkit. Tabular data can be read and edited using it. In this script, the weather dataset is loaded from a CSV file using Pandas, which is then used to execute various data manipulation operations like removing unnecessary columns, filling in blanks, resampling the data, and more.
</li>

<li>
Matplotlib: Python's Matplotlib is a plotting library. It is used to produce numerous chart and plot types. The scatter and line plots in this script are made with Matplotlib.
</li>

<li>
Seaborn: A Python package for data visualisation. It offers a high-level interface for producing illuminating and appealing statistical visuals and is built on top of Matplotlib. In this script, scatter and line plots, a pair plot, and several plots for various months are all made using Seaborn.
</li>

<li>
IPython: Python's interactive programming environment is known as IPython. IPython is used in this script to show HTML code.
</li>
</ul>
<br>
The'read_csv' function is used to load the weather dataset into a Pandas dataframe at the beginning of the script. Then, it carries out a number of data manipulation operations like removing unnecessary columns, filling in blanks, and resampling the data by month. In order to visualise the data, it uses Matplotlib and Seaborn to produce a variety of plots and charts.
This project also imports necessary packages for time series analysis, including NumPy and Statsmodels. It then loads a time series dataset from a Pandas DataFrame, resamples it at daily intervals, and interpolates any missing values. The stationarity of the time series is checked using the Augmented Dickey-Fuller (ADF) test, and a function is defined to plot rolling statistics of the time series.
Since the time series is not stationary, first-order differencing is applied to make it stationary. An ARIMA model is then fit to the differenced time series using order (1, 1, 1). The model summary is printed, and a forecast is generated for the next two years of the time series. The forecasted values are cumulatively summed and added to the last value of the original time series.
Finally, the original time series and the forecasted values are plotted using Matplotlib.

<br>

<h2>Algorithm:</h2>
<br>
<h3>Algorithm/pseudocode for analysis and visualization:</h3>
<ol>
<li>
Import pandas library and read the CSV file containing weather data
</li>
<li>
Use the "head()" function to display the first 50 rows of the dataframe
</li>
<li>
Use the "describe()" function to get statistical summary of the data
</li>
<li>
Use the "info()" function to get the summary of the dataframe including the number of non-null values for each column
</li>
<li>
Sort the data by the "Formatted Date" column using "sort_values()" function
</li>
<li>
Remove irrelevant columns using "drop()" function
</li>
<li>
Check for missing values in the dataframe using "isnull()" function and filter for columns with missing values using "any()" function
</li>
<li>
Fill missing values in the "Precip Type" column with "Not Defined" using the "fillna()" function
</li>
<li>
Convert the "Formatted Date" column to datetime format and set it as the index column using "set_index()" function
</li>
<li>
Resample the data to monthly frequency using the "resample()" function
</li>
<li>
Use seaborn library for data visualization
</li>
<li>
Plot scatterplot of "Apparent Temperature (C)" against "Humidity" using "relplot()" function
</li>
<li>
Plot line graph of "Wind Speed (km/h)" against "Humidity" using "relplot()" function
</li>
<li>
Plot pairplot of "Apparent Temperature (C)" against "Humidity" with respect to "Summary" using "pairplot()" function
</li>
<li>
Plot facetgrid of "Apparent Temperature (C)" against "Humidity" with respect to "Summary" using "relplot()" function
</li>
<li>
Plot line graphs of "Humidity" and "Apparent Temperature (C)" with respect to year using "plot()" function
</li>
<li>
Create a separate dataframe for each month of the year
</li>
<li>
Plot line graphs of "Humidity" and "Apparent Temperature (C)" for each month using "plot()" function.
</li>
</ol>
<br>
<ol>
<h3>Algorithm/pseudocode for forecasting and visualization:</h3>
<li>
Import the required libraries - numpy, statsmodels.
</li>
<li>
Load the time series data into a dataframe and set the index to 'Formatted Date'.
</li>
<li>
Resample the data at daily frequency and interpolate the missing values.
</li>
<li>
Plot the time series using matplotlib.pyplot.
</li>
<li>
Define a function 'test_stationarity' that takes the time series data as input and performs the following steps:
<ol>
<li>
Determine rolling mean and rolling standard deviation of the time series.
</li>
<li>
Plot the rolling mean and rolling standard deviation along with the original time series.
</li>
<li>
Perform the Augmented Dickey-Fuller (ADF) test on the time series and print the test results.
</li>
</ol>
</li>
<li>
Call the 'test_stationarity' function on the original time series.
</li>
<li>
Create a differenced time series by taking the first order difference of the original time series.
</li>
<li>
Call the 'test_stationarity' function on the differenced time series.
</li>
<li>
Fit an ARIMA model to the differenced time series using the statsmodels ARIMA model.
</li>
<li>
Forecast the next 2 years of the time series using the fitted ARIMA model.
</li>
<li>
Plot the original time series along with the forecasted values using matplotlib.pyplot.
</li>
</ol>
<br>
<h2>Dataset:</h2>
<a href="http://www.kaggle.com/datasets/muthuj7/weather-dataset">Click here for the Dataset</a>
<br>
<h2>Architecture:</h2>
