# Predict Future Sales

### Group Members
- 李俊毅 | 106753020
- 戴冕　 | 106703018
- 林琖崴 | 106703043
- 黃浩瑋 | 106703055

### Goal
- You are provided with daily historical sales data. 
- The task is to forecast the total amount of products sold in every shop for the test set.

### DataSet
- [From This Kaggle Competition](https://www.kaggle.com/c/competitive-data-science-predict-future-sales/overview)

## Data
Link: https://www.kaggle.com/c/competitive-data-science-predict-future-sales/data
- File descriptions
  - sales_train.csv - the training set. Daily historical data from January 2013 to October 2015.
  - test.csv - the test set. You need to forecast the sales for these shops and products for November 2015.
  - sample_submission.csv - a sample submission file in the correct format.
  - items.csv - supplemental information about the items/products.
  - item_categories.csv  - supplemental information about the items categories.
  - shops.csv- supplemental information about the shops.
- Data fields
  - ID - an Id that represents a (Shop, Item) tuple within the test set
  - shop_id - unique identifier of a shop
  - item_id - unique identifier of a product
  - item_category_id - unique identifier of item category
  - item_cnt_day - number of products sold. You are predicting a monthly amount of this measure
  - item_price - current price of an item
  - date - date in format dd/mm/yyyy
  - date_block_num - a consecutive month number, used for convenience. January 2013 is 0, February 2013 is 1,..., October 2015 is 33
  - item_name - name of item
  - shop_name - name of shop
  - item_category_name - name of item category
  
- Preprocessing
  - 異常值處理
  - shop值處理
        - 相同shop合併
        - shop劃分為city和category
        - 出現頻率低的category用etc表示
  - item_categories進行分類/篩選
  - item_name進行細分/篩選



## Evaluation Method
- [RMSE (root-mean-square error)](https://en.wikipedia.org/wiki/Root-mean-square_deviation)

## Models

#### XGBoost Regressor
- RMSE: 0.89604

#### Ensemble Model
- Use Bagging/Boosting/Stacking Strategy
  - Ensemble Random Forest/SVD Regressor/Ridge Regressor
    - RMSE (respectively): 1.01704/1.06846/1.07151
  - Final layer use Linear Regressor
    - RMSE: 0.90700
  
#### Null Model
- Use the mean (0.286274) of our prediction
  - RMSE: 1.21744

## Result
- [Slide Presentation](https://docs.google.com/presentation/d/1423q9cYH-ZGHwKdxQz7N30RySXzb6yj5t1AMYe7mYMM/edit?usp=sharing)
- Ranking at 1018 place with RMSE 0.89604

## References

#### Reference Code
- https://www.kaggle.com/rrrrrikimaru/create-model-simple-e-to-e-eda-to-ensemble
- https://medium.com/yuying%E7%9A%84%E4%BD%9C%E5%93%81%E9%9B%86/python-%E7%94%A2%E5%93%81%E9%8A%B7%E5%94%AE%E9%87%8F%E9%A0%90%E6%B8%AC-with-code-kaggle-top-6-8a15f852e874

#### Used Packages
- Numpy, Pandas, Matplotlib, Seaborn
- https://xgboost.readthedocs.io/en/latest/python/python_api.html
- https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.RandomizedSearchCV.html
- https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.SGDRegressor.html
- https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Ridge.html
- https://scikit-learn.org/stable/modules/generated/sklearn.feature_selection.SelectFromModel.html
- https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html
- https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html

#### Related Publication
- https://towardsdatascience.com/how-powerful-can-an-ensemble-of-linear-models-be-231824de50e1
- https://rpubs.com/skydome20/R-Note16-Ensemble_Learning
- http://violin-tao.blogspot.com/2018/01/ml-ensemble.html
- https://www.analyticsvidhya.com/blog/2019/12/6-powerful-feature-engineering-techniques-time-series/

