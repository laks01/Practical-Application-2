               
               
# Practical-Application-2

 
 
 ## What drives the price of a car?
 
**OVERVIEW**

In this application, you will explore a dataset from kaggle. The original dataset contained information on 3 million used cars. The provided dataset contains information on 426K cars to ensure speed of processing. Your goal is to understand what factors make a car more or less expensive. As a result of your analysis, you should provide clear recommendations to your client -- a used car dealership as to what consumers value in a used car

### CRISP-DM Framework

<center>
    <img src = images/crisp.png width = 50%/>
</center>

To frame the task, throughout our practical applications we will refer back to a standard process in industry for data projects called CRISP-DM.  This process provides a framework for working through a data problem.  Your first step in this application will be to read through a brief overview of CRISP-DM [here](https://mo-pcco.s3.us-east-1.amazonaws.com/BH-PCMLAI/module_11/readings_starter.zip).  After reading the overview, answer the questions below.

### Business Understanding

From a business perspective, we are tasked with identifying key drivers for used car prices. We need to provide what used car features influences used car prices


### Data Understanding

After considering the business understanding here are few steps I did to understand the data. 

Vehicles has **426880 rows and 18 columns**. Here is 


<img src = images/vehicle_info.png width = 50%/>


You can find the data exploration code in this notebook [Data Understanding](https://github.com/laks01/Practical-Application-2/blob/main/notebooks/data_understanding.ipynb) 


### Data Preparation

As part of data preparation did these steps to clean up the data:

 * Removed the null values
 * Dropped the null values in these columns : Manufacturer, Model, fuel, odometer, transmission, year 
 * Removed VIN column it is not useful to caluclate price
 * Removedthe outliers after checking the variances
 * Converted categorical variable to numeric
 
 You can find the data preparation code in this notebook [Data Preparation](https://github.com/laks01/Practical-Application-2/blob/main/notebooks/data_preparation.ipynb)
 
 
 ### Feature Engineering
 
 As part of feature engineering did these steps:
 
 * checked the variance vehicles and dropped the columns with less variance.
 * normalized the pricing data.
 * Scaled the numerical data using Standard Scalar
 
<img src = images/correlation.png width = 100%/>

You can find the code for feature engineering in this notebook [Feature Engineering](https://github.com/laks01/Practical-Application-2/blob/main/notebooks/feature_engineering.ipynb)


### Modelling 

As part of modeling followed these steps
 * Split the data into training and test datasets. 
 * Selecting features for model performance
 
 
 
 Experiemented with these models:

* Linear Regression Model
* Ridge Regression Model
* Lasso Regression Model


### Evaluation 

<table>
    <tr>
        <th>Model</th>
        <th>Mean Squared Error</th>
        <th>Mean Absolute Error</th>
     <tr>
     <tr>
        <th>Linear Regression</th>
        <td>83298421.50027786</td>
        <td>7207.934909240748</td>
     <tr>
      <tr>
        <th>Ridge Regression</th>
        <td>83050497.35168709</td>
        <td>7198.752387703689</td>
     <tr> 
     <tr>
        <th>Lasso Regression</th>
        <td>83159076.68200953</td>
        <td>7206.674233794362</td>
     <tr>
    
<table>

You can find the code for modeling in this notebook [Modeling](https://github.com/laks01/Practical-Application-2/blob/main/notebooks/modeling.ipynb)
    

  ### Conclusion
    
  Linear Regression and Ridge Regression performed well. The features 'Year', 'condition', 'cylinder' impacted the car prices. The car dealership should focus on these features while purchasing or selling the cars to the customers.