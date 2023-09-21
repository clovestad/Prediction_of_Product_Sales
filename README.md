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

 - For the testing set on the model, 50% of the variance in y was explained by x.

 - The Mean Absolute Error was off by about $851.63.

 - The Mean Squared Error was $1,378,859.

 - The Root Mean Squared Error had a calculation of $1,174.24.



## Project 1 Revisited
![image](https://github.com/clovestad/Prediction_of_Product_Sales/assets/103072823/195b228c-ab35-4d4f-8af8-34765e943a49)


### top 3 -
- positive effect:
    - outlet_size_medium: for every point increase, an additional 805.36 predicted sales can be assumed.
    - outlet_size_high: for every point increast an additional 441.82 predicted sales can be assumed.
- negative effect:
    - item_visibility: for every point decreased  a reduction in visibility an expected loss of 3,589.50 in outlet sales can be assumed.


- ![image](https://github.com/clovestad/Prediction_of_Product_Sales/assets/103072823/d321ab08-97f5-406e-adc3-e4ce166c2130)
### Interpretation
 ### top 5 most important features
1. item_mrp
2. item_weight
3. item_visibility
4. outlet size - medium
5. outlet size - small

# Explaing model with shap.

![image](https://github.com/clovestad/Prediction_of_Product_Sales/assets/103072823/33b981c8-1121-42a9-8df1-a596b50f75da)

vs.

![image](https://github.com/clovestad/Prediction_of_Product_Sales/assets/103072823/4ac408e0-9850-4b3b-8f68-b297afde8d2d)


- the two visuals echo the same importances with one exception.
    - noteably the outlet size medium has been promoted  two levels of importance than in the previous visual.
    - while item_mrp remains ahead of the pack by double in both cases.

![image](https://github.com/clovestad/Prediction_of_Product_Sales/assets/103072823/f84df4c6-e380-4866-a64e-82be7aea99b5)

### Interpretation
1. item_mrp:
    - the higher an items mrp(red),the more likely it is to positivly impact our predictive model.  
2. outlet_size_medium:
    - the  higher count of medium size stores(red)  will positivly impact our prediction.
3. item_weight:
    - a central cluster of our valaues with mixed feature value colors indicates an average/typical impact on the model predictions.


# Local Models


- - item_mrp (selected since it is ranked as the most impactful to predictions.)
- item_weight(selected since the values reflected in the summary plot are bunched up and could use additional clerification.)
- item_visibility(selected to gain additional insight on store placement combined with parameters above leading to higher/lower sales)
the combinations above can give additional insight on larger/bulkier items costing less VS smaller items that cost more and if placement has an overall impact  to the two features.


## Group 1
### lime tabular
![image](https://github.com/clovestad/Prediction_of_Product_Sales/assets/103072823/d35fa0b3-70c5-4a83-afbe-4e7c2245fa6f)

 - the plot above relates the most impactful predictor to be the item MRP and in this group the mrp is negativly effecting the predicted sales.(higher mrp than average)
### Forceplot
![image](https://github.com/clovestad/Prediction_of_Product_Sales/assets/103072823/eb06f8c6-aa18-4fe3-80ae-d31dcc30d8b7)

-the forceplot above also relates that the item_MRP being of significance in pushing the f(x)  left, while it is noted that the other two group criteria(visibility and weight) are pushing right.

## Group 2
### lime tabular
![image](https://github.com/clovestad/Prediction_of_Product_Sales/assets/103072823/bb1d6f9f-5246-48cd-b406-3456eaec083a)

- the plot above relates that the item MRP again  is the largest influencer, this time having a positive effect on the sales predictions.

### Forceplot

![image](https://github.com/clovestad/Prediction_of_Product_Sales/assets/103072823/4011401b-2eb1-481c-800b-8bdb55695c9a)


- the plot above relates that all three of our filtered criteria are contributing to a lower predicted value pushing to the left.











