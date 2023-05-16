# MMSR
`crowdkit.aggregation.classification.m_msr.MMSR` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/classification/m_msr.py#L17)

```python
MMSR(
    self,
    n_iter: int = 10000,
    tol: float = 1e-10,
    random_state: Optional[int] = 0,
    observation_matrix: ... = _Nothing.NOTHING,
    covariation_matrix: ... = _Nothing.NOTHING,
    n_common_tasks: ... = _Nothing.NOTHING,
    n_workers: int = 0,
    n_tasks: int = 0,
    n_labels: int = 0,
    labels_mapping: Dict[Any, int] = _Nothing.NOTHING,
    workers_mapping: Dict[Any, int] = _Nothing.NOTHING,
    tasks_mapping: Dict[Any, int] = _Nothing.NOTHING
)
```

The **Matrix Mean-Subsequence-Reduced Algorithm** (M-MSR) model assumes that workers have different expertise levels and are represented


as a vector of "skills" $s$ which entries $s_i$ show the probability
that the worker $i$ will answer the given task correctly. Having that, we can estimate the probability of each worker via solving a rank-one matrix completion problem as follows:
$$
\mathbb{E}\left[\frac{M}{M-1}\widetilde{C}-\frac{1}{M-1}\boldsymbol{1}\boldsymbol{1}^T\right]
 = \boldsymbol{s}\boldsymbol{s}^T,
$$
where $M$ is the total number of classes, $\widetilde{C}$ is a covariance matrix between
workers, and $\boldsymbol{1}\boldsymbol{1}^T$ is the all-ones matrix which has the same
size as $\widetilde{C}$.


Thus, the problem of estimating the skill level vector $s$ becomes equivalent to the
rank-one matrix completion problem. The M-MSR algorithm is an iterative algorithm for the *robust*
rank-one matrix completion, so its result is an estimator of the vector $s$.
And the aggregation is weighted majority voting with weights equal to
$\log \frac{(M-1)s_i}{1-s_i}$.

Q. Ma and Alex Olshevsky. Adversarial Crowdsourcing Through Robust Rank-One Matrix Completion.
*34th Conference on Neural Information Processing Systems (NeurIPS 2020)*

<https://arxiv.org/abs/2010.12181>

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`n_iter`|**int**|<p>The maximum number of iterations.</p>
`tol`|**float**|<p>The tolerance stopping criterion for iterative methods with a variable number of steps. The algorithm converges when the loss change is less than the `tol` parameter.</p>
`random_state`|**Optional\[int\]**|<p>The seed number for the random initialization.</p>
`_observation_matrix`|**-**|<p>The matrix representing which workers give responses to which tasks.</p>
`_covariation_matrix`|**-**|<p>The matrix representing the covariance between workers.</p>
`_n_common_tasks`|**-**|<p>The matrix representing workers with tasks in common.</p>
`_n_workers`|**-**|<p>The number of workers.</p>
`_n_tasks`|**-**|<p>The number of tasks that are assigned to workers.</p>
`_n_labels`|**-**|<p>The number of possible labels for a series of classification tasks.</p>
`_labels_mapping`|**-**|<p>The mapping of labels and integer values.</p>
`_workers_mapping`|**-**|<p>The mapping of workers and integer values.</p>
`_tasks_mapping`|**-**|<p>The mapping of tasks and integer values.</p>
`labels_`|**Optional\[Series\]**|<p>The task labels. The `pandas.Series` data is indexed by `task` so that `labels.loc[task]` is the most likely true label of tasks.</p>
`skills_`|**Optional\[Series\]**|<p>The workers&#x27; skills. The `pandas.Series` data is indexed by `worker` and has the corresponding worker skill.</p>
`scores_`|**Optional\[DataFrame\]**|<p>The task label scores. The `pandas.DataFrame` data is indexed by `task` so that `result.loc[task, label]` is a score of `label` for `task`.</p>
`loss_history_`|**List\[float\]**|<p>A list of loss values during training.</p>

**Examples:**


```python
from crowdkit.aggregation import MMSR
from crowdkit.datasets import load_dataset
df, gt = load_dataset('relevance-2')
mmsr = MMSR()
result = mmsr.fit_predict(df)
```
## Methods Summary

| Method | Description |
| :------| :-----------|
[fit](crowdkit.aggregation.classification.m_msr.MMSR.fit.md)| Fits the model to the training data.
[fit_predict](crowdkit.aggregation.classification.m_msr.MMSR.fit_predict.md)| Fits the model to the training data and returns the aggregated results.
[fit_predict_score](crowdkit.aggregation.classification.m_msr.MMSR.fit_predict_score.md)| Fits the model to the training data and returns the total sum of weights for each label.
[predict](crowdkit.aggregation.classification.m_msr.MMSR.predict.md)| Predicts the true labels of tasks when the model is fitted.
[predict_score](crowdkit.aggregation.classification.m_msr.MMSR.predict_score.md)| Returns the total sum of weights for each label when the model is fitted.
