##The DIY Guide to XGBoost

[![Analytics](https://ga-beacon.appspot.com/UA-61611403-2/jxieeducation/xgboost?pixel)](https://github.com/igrigorik/ga-beacon)

_Please make [Pull Requests](https://github.com/jxieeducation/DIY-Data-Science/pulls) for good resources, or create [Issues](https://github.com/jxieeducation/DIY-Data-Science/issues) for any feedback! Thanks!_

----------

XGBoost is an implementation of the famous gradient boosting algorithm. It has won numerous [Kaggle competitions](https://twitter.com/sedielem/status/601707990819962880) and stands above the rest as a tool that is fast and performant. 

### Installation
```
pip install xgboost
```
[Compile by hand](https://github.com/dmlc/xgboost/blob/master/doc/python/python_intro.md#install-xgboost) or [R version](https://www.r-project.org/nosvn/pandoc/xgboost.html) or [Windows version](https://xgboost.readthedocs.org/en/latest/build.html#building-on-windows)

----------

###Hello World
#####Go through the basics
* [Python](https://xgboost.readthedocs.org/en/latest/python/python_intro.html), [R](https://xgboost.readthedocs.org/en/latest/R-package/xgboostPresentation.html) or [Command line](https://github.com/dmlc/xgboost/blob/master/demo/binary_classification/README.md) Walkthroughs.
* [XGBoost in Scikit-learn API](https://github.com/dmlc/xgboost/blob/master/demo/guide-python/sklearn_examples.py#L24)

#####Loading data
* XGBoost has a custom data structure called [DMatrix](http://rpackages.ianhowson.com/cran/xgboost/man/xgb.DMatrix.html)
* DMatrix can be constructed from dense matrix (numpy array), sparse matrix (libsvm) or local file
* [Example](https://github.com/dmlc/xgboost/blob/master/doc/python/python_intro.md#data-interface)


#####Setting the parameters 
* XGBoost parameters values are communicated through a dictionary [Example](https://github.com/dmlc/xgboost/blob/master/doc/python/python_intro.md#setting-parameters) 
* [Official documentation of all parameters](http://xgboost.readthedocs.org/en/latest/parameter.html#parameters-for-tree-booster)
* [Explanation of parameters](http://www.slideshare.net/ShangxuanZhang/kaggle-winning-solution-xgboost-algorithm-let-us-learn-from-its-author/57) (slides 57-70, additional explanation)
* [Suggested parameter values](http://www.analyticsvidhya.com/blog/2016/03/complete-guide-parameter-tuning-xgboost-with-codes-python/) (scroll to the General Parameters section) 
* [Parameter tuning script](https://www.kaggle.com/vinhnguyen/rossmann-store-sales/evolutionary-algorithms-for-param-tuning/run/95364) (evolutionary algorithms)

#####Training and Prediction 
* Relatively straight forward API
* [Training Example](http://xgboost.readthedocs.org/en/latest/python/python_intro.html#training)
* [Prediction Example](http://xgboost.readthedocs.org/en/latest/python/python_intro.html#prediction)

#####Tuning XGB
* [Presentation by former Kaggle #1 Owen Zhang](http://www.slideshare.net/odsc/owen-zhangopen-sourcetoolsanddscompetitions1/12) (slides 12 - 13, very useful)
* [Tuning tips](http://xgboost.readthedocs.org/en/latest/param_tuning.html)

----------


###Theory

#####Decision Tree
* XGBoost takes root from decision trees
* [Quora answer](https://www.quora.com/What-is-an-intuitive-explanation-of-a-decision-tree)
* [Mathematical explanation](https://www.cs.cmu.edu/afs/cs/academic/class/15381-s07/www/slides/041007decisionTrees1.pdf)
* [Video tutorial](https://www.youtube.com/watch?v=a5yWr1hr6QY)


#####Gradient Boosting
* Gradient Boosted Trees are a collection of weak decision trees
* [Official explanation](http://xgboost.readthedocs.org/en/latest/model.html)
* [Mathematical explanation](https://chaoticsenses.wordpress.com/2015/09/20/xgboost-a-macroscopic-anatomy/) (Require good math background)


----------


###Advanced Features

#####Early Stopping
* Stop the training if the validation score isn't improving
* [Example](http://xgboost.readthedocs.org/en/latest/python/python_intro.html#early-stopping)
* [Explanation](http://www.slideshare.net/ShangxuanZhang/kaggle-winning-solution-xgboost-algorithm-let-us-learn-from-its-author) (slides 100-101)

#####Linear Boosting
* When a lot of your data is continuous (not categorical), it makes more sense to use linear boosting
* [Stackoverflow answer](http://datascience.stackexchange.com/questions/9483/xgboost-linear-regression-output-incorrect) (explains when to use this feature)
* [Example](http://xgboost.readthedocs.org/en/latest/R-package/xgboostPresentation.html?highlight=linear#linear-boosting)

#####Feature Importance
* Provides insight as to whether a feature is important
* [Example](http://xgboost.readthedocs.org/en/latest/python/python_intro.html#plotting)
* [Example](https://www.kaggle.com/tqchen/otto-group-product-classification-challenge/understanding-xgboost-model-on-otto-data/notebook) (Section 4, Model Understanding)
* [Explanation](http://www.slideshare.net/ShangxuanZhang/kaggle-winning-solution-xgboost-algorithm-let-us-learn-from-its-author\97) (slides 97 - 99)
* [Importance calculation](https://www.kaggle.com/mmueller/liberty-mutual-group-property-inspection-prediction/xgb-feature-importance-python/code) 

#####External memory 
* This feature lets you train on data bigger than your box's RAM (4GB RAM can now train on 20+GB datasets)
* [Introduction](https://github.com/dmlc/xgboost/blob/master/doc/external_memory.md)
* [Example](https://github.com/tqchen/xgboost/blob/master/demo/guide-python/external_memory.py)

#####Distributed training
* XGBoost provides a parallelization option called All Reduce
* [Official explanation](http://xgboost.readthedocs.org/en/latest/tutorial/aws_yarn.html)

###[Super Short Feedback Survey](https://docs.google.com/forms/u/0/d/1pI5C6eYf0BpE_6pF360gKkFsyxgI5iGSvFe4RPS5N9M/) (Pretty please!)
