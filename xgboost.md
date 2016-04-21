##The DIY Guide to XGBoost
XGBoost is an implementation of the famous gradient boosting algorithm. It has won numerous [Kaggle competitions](https://twitter.com/sedielem/status/601707990819962880) and stands above the rest as a tool that is fast and performant. 

### Installation
```
pip install xgboost
```
[Compile by hand](https://github.com/dmlc/xgboost/blob/master/doc/python/python_intro.md#install-xgboost) or [in R](https://www.r-project.org/nosvn/pandoc/xgboost.html) or [for Windows](https://xgboost.readthedocs.org/en/latest/build.html#building-on-windows)

###Hello World
Go through either [Python](https://xgboost.readthedocs.org/en/latest/python/python_intro.html), [R](https://xgboost.readthedocs.org/en/latest/R-package/xgboostPresentation.html) or [Command line](https://github.com/dmlc/xgboost/blob/master/demo/binary_classification/README.md) Walkthroughs.

After you have been familiarized with the syntax, let's try out a simple [example]()

Loading data [example](https://github.com/dmlc/xgboost/blob/master/doc/python/python_intro.md#data-interface)

#####Setting the parameters 
* [example](https://github.com/dmlc/xgboost/blob/master/doc/python/python_intro.md#setting-parameters) 
* [good parameter values](http://www.analyticsvidhya.com/blog/2016/03/complete-guide-parameter-tuning-xgboost-with-codes-python/) (scroll to the General Parameters section) 
* [parameter introduction](http://www.slideshare.net/ShangxuanZhang/kaggle-winning-solution-xgboost-algorithm-let-us-learn-from-its-author)(slides 57-70)

#####Training 




###Theory
[How Decision Trees work]()

#####How Gradient Boosting works
* [Boosting](http://www.analyticsvidhya.com/blog/2016/02/complete-guide-parameter-tuning-gradient-boosting-gbm-python/)
* [Math explanation](https://chaoticsenses.wordpress.com/2015/09/20/xgboost-a-macroscopic-anatomy/)
 
#####How to Tune XGB
* [Presentation by former Kaggle #1 Owen Zhang](http://www.slideshare.net/odsc/owen-zhangopen-sourcetoolsanddscompetitions1) (go to slide 12)

###Great Features

#####Early Stopping
* This lets you stop the training if validation score isn't improving
* [Example](http://xgboost.readthedocs.org/en/latest/python/python_intro.html#early-stopping)
* [Detailed explanation](http://www.slideshare.net/ShangxuanZhang/kaggle-winning-solution-xgboost-algorithm-let-us-learn-from-its-author) (slides 100-101)

#####Feature Importance
* Provides insight as to whether a feature is important
* [Script example](https://www.kaggle.com/tqchen/otto-group-product-classification-challenge/understanding-xgboost-model-on-otto-data/notebook) (Section 4, Model Understanding)
* [Explanation](http://www.slideshare.net/ShangxuanZhang/kaggle-winning-solution-xgboost-algorithm-let-us-learn-from-its-author) (slides 97 - 99)

#####External memory 
* This feature lets you train on data bigger than your box's RAM
* [Introduction](https://github.com/dmlc/xgboost/blob/master/doc/external_memory.md)
* [Example](https://github.com/tqchen/xgboost/blob/master/demo/guide-python/external_memory.py)


