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
- top 3 -
    - outlet size:
- positive effect:
    - outlet_size_medium: if the store falls into the category of a meduim sized store(based on overall size of ground area covered of the location), an additional 805.36 predicted sales can be assumed.
    - outlet_size_high: if the store falls into the category of a high/large sized store(based on overall size of ground area covered of the location) an additional 441.82 predicted sales can be assumed.
- negative effect:
    - item_visibility: for every point increase in the total overall percentage of total product display space(for that specific product) an expected loss of 3,589.50 in outlet sales can be assumed.
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

 the two examples  we will be displaying  are :
 - products that are -  higher / lower  than average item_mrp
                        higher / lower  than average item_weight
                        higher / lower  than average item_visibility

- group 1 will encompass the less expensive, larger, and less visable items.

- group 2 will encompass the more expansive, smaller, and more visable items.

    
## Group 1
### lime tabular
![image](https://github.com/clovestad/Prediction_of_Product_Sales/assets/103072823/ed9bc06f-a9ab-4faa-ba51-48c30e934f47)

### interpretations

- the plot above relates that the item mrp, the item type being of a breakfast type  and a item type being a hard drink  would reduce the predicted value of the item. While the item  visibility ,item type being breads,and the item type being a starchy food are  influencers toward the item having a higher value.

### Forceplot
![image](https://github.com/clovestad/Prediction_of_Product_Sales/assets/103072823/cdf95cdb-82b7-4508-98ff-7ca4ba0b24d6)

### interpretations

- the plot above relates that this items main influences toward a higher predictions are item  visibility, item weight and having this item be sold in a medium sized store while item_mrp is opposing that force, at a smaller magnitude(not lowering the overall prediction). 

## Group 2
### lime tabular
![image](https://github.com/clovestad/Prediction_of_Product_Sales/assets/103072823/745f6226-6faa-44ca-923f-29b3773c14d1)

### interpretations

- the plot relates that this items main influence for a higher prediction is the item mrp, the item being of a breakfast type, and the item type of being a soft drink.
- the plot  also relates ann additional loss in predicted value in outlet size for all three categories of store(small(146.57)/medium(18111)/large(204.22)) the largest loss occuring in the large store,relating that this particular item would be best suited for a small store.

### Forceplot

![image](https://github.com/clovestad/Prediction_of_Product_Sales/assets/103072823/7b1d9617-5943-488b-a7f9-acd1057a3ee9)

### interpretations

- the plot above relates ther largest contributors to the loss in projected value for this item  to being a medium sized store and item weight.
- the item mrp while being the largest positive contributor was not enought to increase predicted value.











