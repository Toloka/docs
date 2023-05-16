# ZeroBasedSkill
`crowdkit.aggregation.classification.zero_based_skill.ZeroBasedSkill` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/classification/zero_based_skill.py#L14)

```python
ZeroBasedSkill(
    self,
    n_iter: int = 100,
    lr_init: float = 1.0,
    lr_steps_to_reduce: int = 20,
    lr_reduce_factor: float = 0.5,
    eps: float = 1e-05
)
```

The **Zero-Based Skill** (ZBS) aggregation model performs weighted majority voting on tasks. After processing a pool of tasks,


it re-estimates the workers' skills with a gradient descend step to optimize
the mean squared error of the current skills and the fraction of responses that
are equal to the aggregated labels.

This process is repeated until the labels change or exceed the number of iterations.

{% note info %}

It is necessary that all workers in the dataset that is sent to `predict` exist in responses to
the dataset that was sent to `fit`.

{% endnote %}

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`n_iter`|**int**|<p>The maximum number of iterations.</p>
`lr_init`|**float**|<p>The initial learning rate.</p>
`lr_steps_to_reduce`|**int**|<p>The number of steps required to reduce the learning rate.</p>
`lr_reduce_factor`|**float**|<p>The factor by which the learning rate will be multiplied every `lr_steps_to_reduce` step.</p>
`eps`|**float**|<p>The convergence threshold.</p>
`skills_`|**Optional\[Series\]**|<p>The workers&#x27; skills. The `pandas.Series` data is indexed by `worker` and has the corresponding worker skill.</p>
`labels_`|**Optional\[Series\]**|<p>The task labels. The `pandas.Series` data is indexed by `task` so that `labels.loc[task]` is the most likely true label of tasks.</p>
`probas_`|**Optional\[DataFrame\]**|<p>The probability distributions of task labels. The `pandas.DataFrame` data is indexed by `task` so that `result.loc[task, label]` is the probability that the `task` true label is equal to `label`. Each probability is in the range from 0 to 1, all task probabilities must sum up to 1.</p>

**Examples:**


```python
from crowdkit.aggregation import ZeroBasedSkill
from crowdkit.datasets import load_dataset
df, gt = load_dataset('relevance-2')
result = ZeroBasedSkill().fit_predict(df)
```
## Methods Summary

| Method | Description |
| :------| :-----------|
[fit](crowdkit.aggregation.classification.zero_based_skill.ZeroBasedSkill.fit.md)| Fits the model to the training data.
[fit_predict](crowdkit.aggregation.classification.zero_based_skill.ZeroBasedSkill.fit_predict.md)| Fits the model to the training data and returns the aggregated results.
[fit_predict_proba](crowdkit.aggregation.classification.zero_based_skill.ZeroBasedSkill.fit_predict_proba.md)| Fits the model to the training data and returns the aggregated results.
[predict](crowdkit.aggregation.classification.zero_based_skill.ZeroBasedSkill.predict.md)| Predicts the true labels of tasks when the model is fitted.
[predict_proba](crowdkit.aggregation.classification.zero_based_skill.ZeroBasedSkill.predict_proba.md)| Returns probability distributions of labels for each task when the model is fitted.
