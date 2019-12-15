# Chemical_compound
##### Problem Statement:
The given dataset contains details about organic chemical compounds including their chemical features, isomeric conformation, names and the classes in which they are classified. The compounds are classified as either ‘Musk’ or ‘Non-Musk’ compounds.

##### Initial info
>1. No. of sample            : 6598
>2. No. of Feature           : 169
>3. No. of numerical feature : 166
>3. No of classes            : 2 (labels arre 0 & 1)
>4. samples per Class  : 5581 & 1017 for class 0 & 1 respectively
>5. class Distribution : Highly Imbalance
>6. Missing Values     : None

##### Real world constraints
>* Minimise binary class error
>* Probability estimates
>* Average time constraint(i.e few Minutes)


##### Mapping Real world problem to ML problem
>* Type of problem : Binary Classification
>* Performance Metrics : 1:) AUC and 2:) Confusion Matrix
##### ML Constraint
>1.  TPR  must be high
>2.  class probability needed

>* Before performing any kinda univarite or multivariate analysis as soon as I found that dataset is highly imbalance my intution (based on past experience) said me to go for ensembles directly. As one of obvious choice I decided to go for xgboost because it's a great implementation with great ideas in hyper-parameter like row_sampling, column-samling by level.

>* Before Tunning all the hyperparameter decided to tune only number of base estimators and max depth by setting all the remaining paramerers to default values.

##### Preprocessing
>* There are only 2 non-numerical feature so simply dropped it. Definately they could have conained important inormation but thought to give it a try if things will not work i'll try by converitn these features using response coding
>* There is one column name ID seems like identifier so simply removed
>* Seperated out the class column (it is label field)
>* As our base learners will be decision trees so no need to perform standardization
>* Splited the dataset into 80:20 ratio for training and validation, Fixed seed value for reproducible result. splited using stratify so class disb can be in same ratio.

##### Training/ Hyperparameter tunning
>* Used 3 fold cross-Validation
>* values for estimators : [150,250,350,500]
>* values for max_depth  : [1,2,3,4,5]
>* Images for tunning
|COL1|COL2|
|-------------|-------------|
|!['Reload'](https://github.com/vbrail/Chemical_compound/blob/master/images/newplot%20(1).png)|!['Reload'](https://github.com/vbrail/Chemical_compound/blob/master/images/newplot%20(2).png)|
|-------------|-------------|
|![alt text](https://github.com/vbrail/Chemical_compound/blob/master/images/newplot%20(3).png)|![alt text](https://github.com/vbrail/Chemical_compound/blob/master/images/newplot.png)|




