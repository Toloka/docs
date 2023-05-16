# MajorityVote
`crowdkit.aggregation.classification.majority_vote.MajorityVote` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/classification/majority_vote.py#L12)

```python
MajorityVote(
    self,
    on_missing_skill: str = 'error',
    default_skill: Optional[float] = None
)
```

The **Majority Vote** aggregation algorithm is a straightforward approach for categorical aggregation: for each task,


it outputs a label with the largest number of responses. Additionaly, the Majority Vote
can be used when different weights are assigned to workers' votes. In this case, the
resulting label will have the largest sum of weights.


{% note info %}

 If two or more labels have the largest number of votes, the resulting
 label will be the same for all tasks that have the same set of labels with the same number of votes.

 {% endnote %}

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`default_skill`|**Optional\[float\]**|<p>Default worker weight value.</p>
`labels_`|**Optional\[Series\]**|<p>The task labels. The `pandas.Series` data is indexed by `task` so that `labels.loc[task]` is the most likely true label of tasks.</p>
`skills_`|**Optional\[Series\]**|<p>The workers&#x27; skills. The `pandas.Series` data is indexed by `worker` and has the corresponding worker skill.</p>
`probas_`|**Optional\[DataFrame\]**|<p>The probability distributions of task labels. The `pandas.DataFrame` data is indexed by `task` so that `result.loc[task, label]` is the probability that the `task` true label is equal to `label`. Each probability is in the range from 0 to 1, all task probabilities must sum up to 1.</p>
`on_missing_skill`|**str**|<p>A value which specifies how to handle assignments performed by workers with an unknown skill. Possible values:         * &quot;error&quot; — raises an exception if there is at least one assignment performed by a worker with an unknown skill;         * &quot;ignore&quot; — drops assignments performed by workers with an unknown skill during prediction. Raises an exception if there are no         assignments with a known skill for any task;         * value — the default value will be used if a skill is missing.</p>

**Examples:**

Basic Majority Vote:
```python
from crowdkit.aggregation import MajorityVote
from crowdkit.datasets import load_dataset
df, gt = load_dataset('relevance-2')
result = MajorityVote().fit_predict(df)
```
Weighted Majority Vote:
```python
import pandas as pd
from crowdkit.aggregation import MajorityVote
df = pd.DataFrame(
    [
        ['t1', 'p1', 0],
        ['t1', 'p2', 0],
        ['t1', 'p3', 1],
        ['t2', 'p1', 1],
        ['t2', 'p2', 0],
        ['t2', 'p3', 1],
    ],
    columns=['task', 'worker', 'label']
)
skills = pd.Series({'p1': 0.5, 'p2': 0.7, 'p3': 0.4})
result = MajorityVote.fit_predict(df, skills)
```
## Methods Summary

| Method | Description |
| :------| :-----------|
[fit](crowdkit.aggregation.classification.majority_vote.MajorityVote.fit.md)| Fits the model to the training data.
[fit_predict](crowdkit.aggregation.classification.majority_vote.MajorityVote.fit_predict.md)| Fits the model to the training data and returns the aggregated results.
[fit_predict_proba](crowdkit.aggregation.classification.majority_vote.MajorityVote.fit_predict_proba.md)| Fits the model to the training data and returns probability distributions of labels for each task.
