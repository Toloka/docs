# RASA
`crowdkit.aggregation.embeddings.rasa.RASA` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/embeddings/rasa.py#L21)

```python
RASA(
    self,
    n_iter: int = 100,
    tol: float = 1e-09,
    alpha: float = 0.05
)
```

The **Reliability Aware Sequence Aggregation** (RASA) algorithm consists of three steps.


**Step 1**. Encode the worker answers into embeddings.

**Step 2**. Estimate the *global* workers' reliabilities $\beta$ by iteratively performing two steps:
1. For each task, estimate the aggregated embedding: $\hat{e}_i = \frac{\sum_k
\beta_k e_i^k}{\sum_k \beta_k}$
2. For each worker, estimate the global reliability: $\beta_k = \frac{\chi^2_{(\alpha/2,
|\mathcal{V}_k|)}}{\sum_i\left(\|e_i^k - \hat{e}_i\|^2\right)}$, where $\mathcal{V}_k$
is a set of tasks completed by the worker $k$.

**Step 3**. Estimate the aggregated result. It is the output which embedding is
the closest one to $\hat{e}_i$.

Jiyi Li, Fumiyo Fukumoto. A Dataset of Crowdsourced Word Sequences: Collections and Answer Aggregation for Ground Truth Creation.
In *Proceedings of the First Workshop on Aggregating and Analysing Crowdsourced Annotations for NLP*,
Hong Kong, China (November 3, 2019), 24–28.
<https://doi.org/10.18653/v1/D19-5904>

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`n_iter`|**int**|<p>The maximum number of iterations.</p>
`tol`|**float**|<p>The tolerance stopping criterion for iterative methods with a variable number of steps. The algorithm converges when the loss change is less than the `tol` parameter.</p>
`alpha`|**float**|<p>The significance level of the chi-squared distribution quantiles in the $\beta$ parameter formula.</p>
`embeddings_and_outputs_`|**DataFrame**|<p>The task embeddings and outputs. The `pandas.DataFrame` data is indexed by `task` and has the `embedding` and `output` columns.</p>
`loss_history_`|**List\[float\]**|<p>A list of loss values during training.</p>

**Examples:**


```python
import numpy as np
import pandas as pd
from crowdkit.aggregation import RASA
df = pd.DataFrame(
    [
        ['t1', 'p1', 'a', np.array([1.0, 0.0])],
        ['t1', 'p2', 'a', np.array([1.0, 0.0])],
        ['t1', 'p3', 'b', np.array([0.0, 1.0])]
    ],
    columns=['task', 'worker', 'output', 'embedding']
)
result = RASA().fit_predict(df)
```
## Methods Summary

| Method | Description |
| :------| :-----------|
[fit](crowdkit.aggregation.embeddings.rasa.RASA.fit.md)| Fits the model to the training data.
[fit_predict](crowdkit.aggregation.embeddings.rasa.RASA.fit_predict.md)| Fits the model to the training data and returns the aggregated outputs.
[fit_predict_scores](crowdkit.aggregation.embeddings.rasa.RASA.fit_predict_scores.md)| Fits the model to the training data and returns the estimated scores.
