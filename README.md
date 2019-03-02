# santander-customer-transaction-prediction
repository for the Kaggle competition santander-customer-transaction-prediction

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
| 2019-02-29      | lgb add 200 columns with rank (avg, pct=true) | 0.896 | 0.89292  |
| 2019-02-29      | lgb add 200 columns with rank (avg, pct=true) but fe with train and test together | 0.896 | 0.89287  |