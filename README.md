# Predicting Meat Futures
Assuming we are in a farming role we want to be able to predict the seasonality of chicken and potentially buy chicken futures when the prices are going to be the lowest. We also want to use both the Facebook Prophet time-series machine learning model and the XGBoost regression machine learning model to predict what the price will be in one year and three years.

## Technologies

Language: Python 3.7

Libraries used:

[Pandas](https://pandas.pydata.org/pandas-docs/stable/index.html) - For the creation and visualization of Data Frames

[Jupyter Labs](https://jupyter.org/) - An ipython kernel for interactive computing in python

[PyViz hvPlot](https://hvplot.holoviz.org/index.html) - A high level python library for interactive data visualization

[Scikit-Learn](https://scikit-learn.org/0.18/auto_examples/svm/plot_iris.html) - Powerful machine learning library

[Facebook Prophet](https://facebook.github.io/prophet/) - Industry gold standard for predicting time-series models

[XGBoost](https://xgboost.readthedocs.io/en/stable/) - Another industry standard machine learning tool similar to Random Forests 


## Installation Guide

If you are using an anaconda or a conda environment (which is highly recommended) chances are pandas, hvplot and jupyter labs are already installed in your virtual environment. In addition, installing Facebook's Prophet library will be necessary

For a full install activate a conda development environment and run in GitBash if not already installed, otherwise pip can be used:
```python
    conda install pandas
    conda install jupyterlab
    conda install -c pyviz hvplot
```

To install the other dependencies not included in the anaconda environment run:
```python
    conda install prophet
    conda install -c conda-forge py-xgboost 
    conda install -c intel scikit-learn
```

Check the to make sure everything has been installed properly
```python
    conda list pandas
    conda list hvplot
    conda list jupyter lab
    conda list prophet
    conda list xgboost
    conda list scikit-learn
```
---

## Pros and Cons of Prophet Compared to XGBoost

* XGBoost overfit the data 
* XGBoost did not weigh the increase in year heavy enough when creating predictions, does not pick up on increasing trend
* XGBoost kind of recognized a seasonality to the data, but it does not entirely line up with Prophet
* Prophet makes a reasonable looking predictive model for the future


---

## Similarities and Differences

**XGBoost picked up on some seasonality** - The peaks lie between months 4-6 and the dips are in January of each year
<div style="text-align: left"><img src="./images/seasonality_xgboost.png" width="500" /></div>

**Prophet** - Has a seasonality function built in to its software
<div style="text-align: left"><img src="./images/seasonality_trends.png" width="700" /></div>


---

## Summary of Seasonality Predictions
#### We can see that chicken prices appear to spike in late February and are at their lowest in April on a yearly basis. There is another run during the summer lasting through September of each year. 

***It would be best to buy chicken futures at two points:*** 
> 1. After September in hopes of capitalizing on the spike in late February.
> 2. Directly after the drop around April to get in a good position for the summer surge.


---

### Prophet:
**Predictions 3 Years** <div style="text-align: left"><img src="./images/prophet_three_changepoints.png" width="700" /></div>


### XGBoost:
**Simple Features:** <div style="text-align: left"><img src="./images/simple_features.png" width="100" /></div><div style="text-align: left"><img src="./images/simple_feature_plot.png" width="800" /></div>

**Mulitple Features:** <div style="text-align: left"><img src="./images/multi_feature.png" width="300" /></div><div style="text-align: left"><img src="./images/three_year_plot.png" width="800" /></div>

### Summary of Prophet and XGBoost Three Year Predictions
* Prophet expects the price to come back down to its average linear regression line after its major spike to an average price of $3.5/pound.
* Prophet shows us a critical point where the volatility in chicken prices has been steadily increasing since the point marked in red around 2017.
* XGBoost does not pick up on the average increase of price per year, but does show us that a price reduction is likely to happen as well.
* Overall it seems apparent that chicken prices could be largely inflated and may be slated to drop in the near future. 
* Buying chicken futures now may prove to be a risky decision and we may want to wait until the price retracts to its normal predicted amount before investing.


## Collaborator Information

David Hutsell
> email: dhutsellcfncw@gmail.com |
> [Git Hub](https://github.com/dhut1621) |
> [LinkedIn](https://www.linkedin.com/in/david-hutsell-4b013795/) 

Ryan Svendson
> email: rsvendson@gmail.com |
> [Git Hub](https://github.com/RyanSvendson) |
> [LinkedIn](https://www.linkedin.com/in/ryan-svendson-cfp/)

Saidee Padilla
> email: SPadilla51@bigbend.edu |
> [Git Hub](https://github.com/saideepadilla) |
> [LinkedIn](https://www.linkedin.com/in/saidee-padilla-127684247/) 

Silvano Ross: 
> email: silvanoross3@gmail.com |
> [GitHub](https://github.com/silvanoross) |
> [LinkedIn](https://www.linkedin.com/in/silvano-ross-b6a15a93/)
