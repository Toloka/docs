# Wawa
`crowdkit.aggregation.classification.wawa.Wawa` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/classification/wawa.py#L14)

```python
Wawa(self)
```

The **Worker Agreement with Aggregate** (Wawa) algorithm consists of three steps:


1. calculates the majority vote label;
2. estimates workers' skills as a fraction of responses that are equal to the majority vote;
3. calculates the weigthed majority vote based on skills from the previous step.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`labels_`|**Optional\[Series\]**|<p>The task labels. The `pandas.Series` data is indexed by `task` so that `labels.loc[task]` is the most likely true label of tasks.</p>
`skills_`|**Optional\[Series\]**|<p>The workers&#x27; skills. The `pandas.Series` data is indexed by `worker` and has the corresponding worker skill.</p>
`probas_`|**Optional\[DataFrame\]**|<p>The probability distributions of task labels. The `pandas.DataFrame` data is indexed by `task` so that `result.loc[task, label]` is the probability that the `task` true label is equal to `label`. Each probability is in the range from 0 to 1, all task probabilities must sum up to 1.</p>

**Examples:**


```python
from crowdkit.aggregation import Wawa
from crowdkit.datasets import load_dataset
df, gt = load_dataset('relevance-2')
result = Wawa().fit_predict(df)
```
## Methods Summary

| Method | Description |
| :------| :-----------|
[fit](crowdkit.aggregation.classification.wawa.Wawa.fit.md)| Fits the model to the training data.
[fit_predict](crowdkit.aggregation.classification.wawa.Wawa.fit_predict.md)| Fits the model to the training data and returns the aggregated results.
[fit_predict_proba](crowdkit.aggregation.classification.wawa.Wawa.fit_predict_proba.md)| Fits the model to the training data and returns probability distributions of labels for each task.
[predict](crowdkit.aggregation.classification.wawa.Wawa.predict.md)| Predicts the true labels of tasks when the model is fitted.
[predict_proba](crowdkit.aggregation.classification.wawa.Wawa.predict_proba.md)| Returns probability distributions of labels for each task when the model is fitted.
