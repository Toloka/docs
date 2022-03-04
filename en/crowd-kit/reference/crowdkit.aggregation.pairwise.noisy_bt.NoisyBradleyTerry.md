# NoisyBradleyTerry

`crowdkit.aggregation.pairwise.noisy_bt.NoisyBradleyTerry` | [Source code](https://github.com/Toloka/crowd-kit/blob/main/src/aggregation/pairwise/noisy_bt.py)&nbsp;[![Source code](../../../_images/github-icon.svg "Source code" =20x20)](https://github.com/Toloka/crowd-kit/blob/main/src/aggregation/pairwise/noisy_bt.py)

```python
NoisyBradleyTerry(
    self,
    n_iter: int = 100,
    tol: float = 1e-05,
    random_state: int = 0
)
```

A modification of Bradley-Terry with parameters for performers' skills and
their biases.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`scores_`|**Series**|<p>&#x27;Labels&#x27; scores. A pandas.Series index by labels and holding corresponding label&#x27;s scores</p>
`skills_`|**Series**|<p>Performers&#x27; skills. A pandas.Series index by performers and holding corresponding performer&#x27;s skill</p>
`biases_`|**Series**|<p>Predicted biases for each performer. Indicates the probability of a performer to choose the left item. A series of performers&#x27; biases indexed by performers</p>

## Methods summary

| Method | Description |
| :------| :-----------|
[fit](crowdkit.aggregation.pairwise.noisy_bt.NoisyBradleyTerry.fit.md)| None
[fit_predict](crowdkit.aggregation.pairwise.noisy_bt.NoisyBradleyTerry.fit_predict.md)| None
