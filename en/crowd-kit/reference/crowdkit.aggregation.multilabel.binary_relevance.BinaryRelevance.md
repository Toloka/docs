# BinaryRelevance
`crowdkit.aggregation.multilabel.binary_relevance.BinaryRelevance` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/multilabel/binary_relevance.py#L14)

```python
BinaryRelevance(self, base_aggregator: BaseClassificationAggregator = ...)
```

Simple aggregation algorithm for multi-label classification.


Binary Relevance is a straightforward approach for multi-label classification aggregation:
each label is treated as a class in binary classification problem and aggregated separately using
aggregation algorithms for classification, e.g. Majority Vote or Dawid Skene.

{% note info %}

If this method is used for single-label classification, the output of the BinaryRelevance method may differ
from the output of the basic aggregator used for its intended purpose, since each class generates a binary
classification task, and therefore it is considered separately. For example, some objects may not have labels.

{% endnote %}

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`base_aggregator`|**[BaseClassificationAggregator](crowdkit.aggregation.base.BaseClassificationAggregator.md)**|<p>Aggregator instance that will be used for each binary classification. All class parameters will be copied, except for the results of previous fit.</p>
`labels_`|**Optional\[Series\]**|<p>Tasks&#x27; labels. A pandas.Series indexed by `task` such that `labels.loc[task]` is the tasks&#x27; aggregated labels.</p>
`aggregators_`|**Dict\[str, [BaseClassificationAggregator](crowdkit.aggregation.base.BaseClassificationAggregator.md)\]**|<p>Labels&#x27; aggregators matched to classes. A dictionary that matches aggregators to classes. The key is the class found in the source data, and the value is the aggregator used for this class. The set of keys is all the classes that are in the input data.</p>

**Examples:**


```python
import pandas as pd
from crowdkit.aggregation import BinaryRelevance, DawidSkene
df = pd.DataFrame(
    [
        ['t1', 'w1', ['house', 'tree']],
        ['t1', 'w2', ['house']],
        ['t1', 'w3', ['house', 'tree', 'grass']],
        ['t2', 'w1', ['car']],
        ['t2', 'w2', ['car', 'human']],
        ['t2', 'w3', ['train']]
    ]
)
df.columns = ['task', 'worker', 'label']
result = BinaryRelevance(DawidSkene(n_iter=10)).fit_predict(df)
```
## Methods Summary

| Method | Description |
| :------| :-----------|
[fit](crowdkit.aggregation.multilabel.binary_relevance.BinaryRelevance.fit.md)| Fit the aggregators.
[fit_predict](crowdkit.aggregation.multilabel.binary_relevance.BinaryRelevance.fit_predict.md)| Fit the model and return aggregated results.
