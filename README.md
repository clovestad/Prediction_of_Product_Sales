# Prediction Of Product Sales 

- Sales predictions for various food item sold at many stores.


## Colin Lovestad
 
## Data Source: https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/

## Data Dictionary:
![image](https://github.com/clovestad/Prediction_of_Product_Sales/assets/103072823/010fbd5b-6581-4434-9388-7f19b3c0bb34)

## Data Cleaning
to prepare Data for exploratory Data Analysis, Data has been cleaned to ensure all Null/Duplicated values will not effect overall model performance

## Exploratory Data Analysis
to explore data, various  visualations were used to visualize correlation.

![image](https://github.com/clovestad/Prediction_of_Product_Sales/assets/103072823/cc05c4a9-4a81-47d9-afb6-d7453558d385)

the plot above relates that the 3 most common items sold in stores  are  fruits/veggies, snacks, and household goods.

![image](https://github.com/clovestad/Prediction_of_Product_Sales/assets/103072823/c2e1653e-7758-4456-9740-70f4a35b0fd9)

the plot above  clearly shows that  Type 3 supermarkets Trend a higher outlet sales


![image](https://github.com/clovestad/Prediction_of_Product_Sales/assets/103072823/a8869f03-c684-4510-942b-5e0265e63650)
 
 the plot above shows the correlations between the Maximum listing price fro the product and the  outlet sales, indicating a positive correlation.

 ## Machine learning Models:
 -  Linear Regression Model
 -  Random Forest Regression Model
 -  Tuned Random Forest Regression Model

    1. linear regression (Test set)
      
    ![image](https://github.com/clovestad/Prediction_of_Product_Sales/assets/103072823/ff57c082-2c92-48f9-9997-1b6b84ed86a4)


    2. Random Forest (Test set)

     ![image](https://github.com/clovestad/Prediction_of_Product_Sales/assets/103072823/10ce43ed-35ce-451c-97cb-f19879eb9fdf)


    3. Tuned Random Forest(test set)
  
    ![image](https://github.com/clovestad/Prediction_of_Product_Sales/assets/103072823/96e640f5-daa3-449a-8517-58226a0014fc)
  
    

    ## model performance


    The Final Model Chosen was the Tuned random forest 

For the testing set on the model, 50% of the variance in y was explained by x.

The Mean Absolute Error was off by about $851.63.

The Mean Squared Error was $1,378,859.

The Root Mean Squared Error had a calculation of $1,174.24.
