##The DIY Guide to XGBoost

[![Analytics](https://ga-beacon.appspot.com/UA-61611403-2/jxieeducation/xgboost?pixel)](https://github.com/igrigorik/ga-beacon)


XGBoost is an implementation of the famous gradient boosting algorithm. It has won numerous [Kaggle competitions](https://twitter.com/sedielem/status/601707990819962880) and stands above the rest as a tool that is fast and performant. 

### Installation
```
pip install xgboost
```
[Compile by hand](https://github.com/dmlc/xgboost/blob/master/doc/python/python_intro.md#install-xgboost) or [in R](https://www.r-project.org/nosvn/pandoc/xgboost.html) or [for Windows](https://xgboost.readthedocs.org/en/latest/build.html#building-on-windows)

----------

###Hello World
#####Go through the basics
* [Python](https://xgboost.readthedocs.org/en/latest/python/python_intro.html), [R](https://xgboost.readthedocs.org/en/latest/R-package/xgboostPresentation.html) or [Command line](https://github.com/dmlc/xgboost/blob/master/demo/binary_classification/README.md) Walkthroughs.
* [Scikit-learn API](https://github.com/dmlc/xgboost/blob/master/demo/guide-python/sklearn_examples.py)

#####[Loading data](https://github.com/dmlc/xgboost/blob/master/doc/python/python_intro.md#data-interface)

#####Setting the parameters 
* [Example](https://github.com/dmlc/xgboost/blob/master/doc/python/python_intro.md#setting-parameters) 
* [Official documentation of all parameters](http://xgboost.readthedocs.org/en/latest/parameter.html#parameters-for-tree-booster)
* [Explanation of parameters](http://www.slideshare.net/ShangxuanZhang/kaggle-winning-solution-xgboost-algorithm-let-us-learn-from-its-author) (slides 57-70, pretty much the same as the explanation above)
* [Suggested parameter values](http://www.analyticsvidhya.com/blog/2016/03/complete-guide-parameter-tuning-xgboost-with-codes-python/) (scroll to the General Parameters section) 
* [Parameter tuning script](https://www.kaggle.com/vinhnguyen/rossmann-store-sales/evolutionary-algorithms-for-param-tuning/run/95364) (evolutionary algorithms)

#####[Training](http://xgboost.readthedocs.org/en/latest/python/python_intro.html#training)

#####[Prediction](http://xgboost.readthedocs.org/en/latest/python/python_intro.html#prediction)

#####Tuning XGB
* [Presentation by former Kaggle #1 Owen Zhang](http://www.slideshare.net/odsc/owen-zhangopen-sourcetoolsanddscompetitions1) (slides 12 - 13)
* [Tuning tips](http://xgboost.readthedocs.org/en/latest/param_tuning.html)

#####Extras
* [Simple kaggle script](https://www.kaggle.com/andrelopes1705/santander-customer-satisfaction/first-xgboost-script)
* [Kaggle Higgs Bozon blog post](https://no2147483647.wordpress.com/2014/09/17/winning-solution-of-kaggle-higgs-competition-what-a-single-model-can-do/)


----------


###Theory

#####Decision Tree
* [Quora's intuition](https://www.quora.com/What-is-an-intuitive-explanation-of-a-decision-tree)
* [Simple mathematical explanation](https://www.cs.cmu.edu/afs/cs/academic/class/15381-s07/www/slides/041007decisionTrees1.pdf)
* [Video explanation](https://www.youtube.com/watch?v=a5yWr1hr6QY)


#####Gradient Boosting
* [Official explanation](http://xgboost.readthedocs.org/en/latest/model.html)
* [Boosting](http://www.analyticsvidhya.com/blog/2016/02/complete-guide-parameter-tuning-gradient-boosting-gbm-python/) (Section 1, How Boosting Works)
* [Mathematical explanation](https://chaoticsenses.wordpress.com/2015/09/20/xgboost-a-macroscopic-anatomy/)


----------


###Advanced Features

#####Early Stopping
* This lets you stop the training if validation score isn't improving
* [Example](http://xgboost.readthedocs.org/en/latest/python/python_intro.html#early-stopping)
* [Explanation](http://www.slideshare.net/ShangxuanZhang/kaggle-winning-solution-xgboost-algorithm-let-us-learn-from-its-author) (slides 100-101)

#####Linear Boosting
* When a lot of your data is continuous (not categorical), it makes more sense to use linear boosting
* [Example](http://xgboost.readthedocs.org/en/latest/R-package/xgboostPresentation.html?highlight=linear#linear-boosting)
* [Stackoverflow answer](http://datascience.stackexchange.com/questions/9483/xgboost-linear-regression-output-incorrect) (explains when to use this feature)

#####Feature Importance
* Provides insight as to whether a feature is important
* [Example](http://xgboost.readthedocs.org/en/latest/python/python_intro.html#plotting)
* [Example](https://www.kaggle.com/tqchen/otto-group-product-classification-challenge/understanding-xgboost-model-on-otto-data/notebook) (Section 4, Model Understanding)
* [Explanation](http://www.slideshare.net/ShangxuanZhang/kaggle-winning-solution-xgboost-algorithm-let-us-learn-from-its-author) (slides 97 - 99)
* [Importance calculation](https://www.kaggle.com/mmueller/liberty-mutual-group-property-inspection-prediction/xgb-feature-importance-python/code) (through f-scores)

#####External memory 
* This feature lets you train on data bigger than your box's RAM
* [Introduction](https://github.com/dmlc/xgboost/blob/master/doc/external_memory.md)
* [Example](https://github.com/tqchen/xgboost/blob/master/demo/guide-python/external_memory.py)

#####Distributed training
* XGBoost provides a parallelization option called All Reduce
* [Official explanation](http://xgboost.readthedocs.org/en/latest/tutorial/aws_yarn.html)
