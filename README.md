# santander-customer-transaction-prediction
repository for the Kaggle competition santander-customer-transaction-prediction

## Final results:
My final ranking is **122nd (1.4%)**. What I learnt from this competition is how NN can use to improve performance. According to one of the top team's solution, they created 200 new features based on the original 200 features. To let the nn learn about the potential interactions between each (original, new feature) pair, they changed the input shape to (200,2). This is brilliant. What it does is treating each pair as of two colors in a pixel. So the model knows they belong to each other.


## LB and CV journey

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
| 2019-03-08      | take exp of the features and added 50 cut out of the exp (removed original) | 0.896 | 0.89299 |
| 2019-03-08      | take exp of the features and added 150 cut out of the exp (removed original) | null | 0.89295 |
| 2019-03-12      | rank with 2 decimals (removed original cols) | 0.896 | 0.89303 |
| 2019-03-12      | original plus qcut of 2 | null | 0.89305 |
| 2019-03-12      | kmeans minibatch with k =20 | null | 0.89244 |
| 2019-03-12      | kmeans minibatch with k =20, cluster is categorical feature in lgb | null | 0.89231 |
| 2019-03-21      | random shuffle and upsample once for pos | 0.897 | 0.89381 |
| 2019-03-21      | random shuffle and upsample twice for pos | null | 0.89403 |
| 2019-03-21      | random shuffle and upsample 3 times for pos | null | 0.89417 |
| 2019-03-21      | random shuffle and upsample 9 times for pos | null | 0.8930 |
| 2019-03-21      | random shuffle and upsample 4 times for pos | null | 0.89332 |
| 2019-03-21      | take exp and augment for 3 times | null | 0.8936 |
| 2019-03-21      | take exp and augment for 3 times (changed num_leave to 5) | null | 0.89729 |
| 2019-03-21      | take exp and augment for 0 times (changed num_leave to 5) | null | 0.8934 |
| 2019-03-21      | augment for 3 times (fixed error in the augment function) | 0.899 | 0.89659 |
| 2019-03-21      | augment for 9 times (fixed error in the augment function) | null | 0.89772 |
| 2019-03-21      | augment for 12 times (fixed error in the augment function) | null | 0.89825 |
| 2019-03-21      | augment for 5 times (fixed error in the augment function) | null | 0.89755 |
| 2019-03-21      | exp + augment for 5 times (fixed error in the augment function) | null | 0.89724 |

