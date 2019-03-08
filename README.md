# santander-customer-transaction-prediction
repository for the Kaggle competition santander-customer-transaction-prediction




## Things known so far:
1. the 200 features are un-correlated so it's very likely that they are a result of PCAs
2. the features seem to be normally distributed 


## Score tracking

| Date        | description           | LB  | cv  |
| ------------- |:-------------:| -----:|-----:|
| 2019-02-26      | downloaded data and started EDA |  |  |
| 2019-02-26      | simple logistic with 0,1 normalisation | 0.639 | 0.627  |
| 2019-02-26      | simple lgb without preprocessing. Benchmark | 0.897 | 0.8929  |
| 2019-02-26      | h2o without preprocessing. Benchmark | 0.885 | 0.8853  |
| 2019-02-27      | lgb with simple stats eg min mean std | null | 0.8926  |
| 2019-02-28      | lgb mean of all col and subtrace each col with their col mean | null | 0.89253  |
| 2019-02-28      | lgb median of all col and subtrace each col with their col mean | null | 0.89225  |
| 2019-02-28      | lgb mean subtracts keep all | 0.896 | 0.89279  |
| 2019-02-28      | lgb median and original divided by median. keep all | null | 0.8930  |
| 2019-02-28      | lgb mean and original divided by mean. keep all (wrong) | null | 0.89205  |
| 2019-02-28      | lgb mean and original divided by mean. keep all | null | 0.89221  |
| 2019-02-28      | lgb take the min and max and subtract them for all cols. Each original then divided by them. keep all | null | 0.8928  |
| 2019-02-28      | lgb take the median and max and subtract them for all cols. Each original then divided by them. keep all | null | 0.89279  |
| 2019-03-01      | lgb add 200 columns with rank (avg, pct=true) | 0.896 | 0.89292  |
| 2019-03-01      | lgb add 200 columns with rank (avg, pct=true) but fe with train and test together | 0.896 | 0.89287  |
| 2019-03-04      | retrained the above but results changed. i think it could be the kfold package version difference in my two different computers | null | 0.89279  |
| 2019-03-04      | added some simple stats on the new 200 rank columns and removeed the 200 new rank cols | null | 0.89207  |
| 2019-03-04      | sort each row from largest feature value to the lowest (keep original cols) | null | 0.89214 |
| 2019-03-04      | sort each row from largest feature value to the lowest (remove original cols) | null | 0.5771 |
| 2019-03-04      | top bottom 25 and return index | 0.896 | 0.8928 |
| 2019-03-04      | top bottom 25 and return index (being treated as cat features in lgb) | null | 0.85970  |
| 2019-03-06      | rank pct as weight and then multiply with original | null | 0.89219  |
| 2019-03-06      | each feat we have cut with 50 bins | null | 0.89280  |
| 2019-03-06      | standardise by row | null | 0.89223  |
| 2019-03-07      | power transform and then min max scale (removed original) | 0.893 |  0.89292 |
| 2019-03-08      | take exp of the features (removed original) | 0.897 |  0.89312 |
| 2019-03-08      | take exp of the features (kept original) | null |  0.89276 |
| 2019-03-08      | take exp of the features and added 100 cut out of the exp (removed original) | 0.896 | 0.89347 |
| 2019-03-08      | take exp of the features and added 50 cut out of the exp (removed original) | null | 0.89299 |
| 2019-03-08      | take exp of the features and added 150 cut out of the exp (removed original) | null | 0.89295 |

