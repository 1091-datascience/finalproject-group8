# Predict Future Sales

### Group Members
- 李俊毅 | 106753020
- 戴冕　 | 106703018
- 林琖崴 | 106703043
- 黃浩瑋 | 106703055

### Goal

### DataSet
- [From This Kaggle Competition](https://www.kaggle.com/c/competitive-data-science-predict-future-sales/overview)

## Data

## Evaluation Method
- [RMSE (root-mean-square error)](https://en.wikipedia.org/wiki/Root-mean-square_deviation)

## Models

#### XGBoost Regressor

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
- [Slide Presentation]()
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

