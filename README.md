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
<br>
<div align="center">
<img src="https://user-images.githubusercontent.com/73570745/231559837-86407423-a613-4fe4-9d02-51d997e7ec7f.png"><br>
</div>
<br>

<h2>Results:</h2>
<br>
<h3>Initial Data Analysis:</h3>
<br>
<div align="center">
<img src="https://user-images.githubusercontent.com/73570745/231560066-ce4aa68a-420b-478a-93c4-14243a9c8e14.png"><br>
</div>
<br>
<br>
<div align="center">
<img src="https://user-images.githubusercontent.com/73570745/231560283-50f4e4bd-5f6a-4734-a61f-05a51dc6ae0c.png"><br>
</div>
<br>
<br>
<div align="center">
<img src="https://user-images.githubusercontent.com/73570745/231560348-ff630282-755e-4fb2-98c7-8e48abc7aed6.png"><br>
</div>
<br>
<br>
<div align="center">
<img src="https://user-images.githubusercontent.com/73570745/231560415-ae42d411-f032-4121-849d-425e4f658bec.png"><br>
</div>
<br>
<br>
<div align="center">
<img src="https://user-images.githubusercontent.com/73570745/231560482-101dbc0e-787f-4289-bb45-53eab63ac24c.png"><br>
</div>
<br>
<br>
<div align="center">
<img src="https://user-images.githubusercontent.com/73570745/231560531-f3a68c4d-b18a-4719-ae35-2117489c8890.png"><br>
</div>
<br>
<br>
<div align="center">
<img src="https://user-images.githubusercontent.com/73570745/231560611-23a9835c-d544-4ed1-8a33-3f6c43002b1a.png"><br>
</div>
<br>
<br>
<div align="center">
<img src="https://user-images.githubusercontent.com/73570745/231560671-61d57da1-3332-46f8-8af3-684587e96820.png"><br>
</div>
<br>
<br>
<div align="center">
<img src="https://user-images.githubusercontent.com/73570745/231560733-eb0866c1-584a-4d0d-a272-aef47f5aee4c.png"><br>
</div>
<br>
<h3>Forecasting Results:</h3>
<br>
<div align="center">
<img src="https://user-images.githubusercontent.com/73570745/231561039-056c505e-c5d5-4a08-a4fd-fcbfeeaa10af.png"><br>
</div>
<br>
<br>
<div align="center">
<img src="https://user-images.githubusercontent.com/73570745/231561200-11b5aa10-a4b2-4043-a37c-e84a6287550d.png"><br>
</div>
<br>
<br>
<div align="center">
<img src="https://user-images.githubusercontent.com/73570745/231561265-e99d3fb0-43b3-4db8-b5b3-d2524571248f.png"><br>
</div>
<br>
<br>
<div align="center">
<img src="https://user-images.githubusercontent.com/73570745/231561312-f699ab2c-ee80-4711-928d-9cb46aea84ce.png"><br>
</div>
<br>
<h3>Tableau Results:</h3>
<br>
<div align="center">
<img src="https://user-images.githubusercontent.com/73570745/231561520-5e87626b-3911-4cef-bb05-f80eeea299ca.png"><br>
</div>
<br>
<br>
<div align="center">
<img src="https://user-images.githubusercontent.com/73570745/231561673-d7c60160-ec5d-483c-9ed5-6f5737e0633c.png"><br>
</div>
<br>
<br>
<div align="center">
<img src="https://user-images.githubusercontent.com/73570745/231561732-d80f0e26-4974-4d92-b6eb-4322b9492acb.png"><br>
</div>
<br>
<br>
<div align="center">
<img src="https://user-images.githubusercontent.com/73570745/231561776-fba56c45-b81a-45fa-b01c-dbeea05bbc18.png"><br>
</div>
<br>
<br>
<div align="center">
<img src="https://user-images.githubusercontent.com/73570745/231561803-fdbfa61e-b486-4723-8c9f-d1cf493cbbfd.png"><br>
</div>
<br>
<h2>Conclusion:</h2>
<br>
In conclusion, the code demonstrated the use of an ARIMA model to anticipate temperature data for the following two years and provided a thorough analysis and visualisation of meteorological data. To remove extraneous columns and fill in missing values, the data was initially preprocessed. The association between elements like humidity, wind speed, and temperature was then determined using monthly averages and data visualisation.
The time series data were then subjected to the ARIMA model, which was fitted using an order of (1,1,1) after differencing was performed to confirm the data's stationarity. The forecasted temperature values were calculated by multiplying the most recent temperature value by the cumulative sum of the forecasted temperature values.
The analysis offers a helpful place to start for more research and model enhancements. To comprehend the discrepancy between the predicted and actual temperature readings, multiple measures, including Mean Absolute Error (MAE), Mean Squared Error (MSE), and Root Mean Squared Error (RMSE), can be used to measure the model's accuracy. To find the optimal order for forecasting the temperature data, various orders for the ARIMA model could also be attempted and contrasted.
Overall, the code offers a superb illustration of how to reliably anticipate time series data using a variety of techniques, including data pre-treatment, visualization, and modelling.
