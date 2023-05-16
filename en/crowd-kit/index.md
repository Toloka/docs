# Crowd-Kit

_Computational quality control for crowdsourcing_

**Crowd-Kit** is a powerful Python library that implements commonly-used aggregation methods for crowdsourced annotation and offers the relevant metrics and datasets. We strive to implement functionality that simplifies working with crowdsourced data.

Currently, Crowd-Kit contains:

* implementations of commonly-used aggregation methods for categorical, pairwise, textual, and segmentation responses;
* metrics of uncertainty, consistency, and agreement with aggregate;
* loaders for popular crowdsourced datasets.

## Installing

To install Crowd-Kit, run the following command:

```bash
pip install crowd-kit
```

If you also want to use the `learning` subpackage, type

```bash
pip instal crowd-kit[learning]
```

If you are interested in contributing to Crowd-Kit, use [Pipenv](https://pipenv.pypa.io/en/latest/) to install the library with its dependencies:

```bash
pipenv install --dev
```

We use [pytest](https://docs.pytest.org/en/7.1.x/) for testing.

## Getting started

This example shows how to use Crowd-Kit for categorical aggregation using the classical Dawid-Skene algorithm.

First, let us do all the necessary imports.

````python
from crowdkit.aggregation import DawidSkene
from crowdkit.datasets import load_dataset
import pandas as pd
````

Then, you need to read your annotations into Pandas DataFrame with columns `task`, `worker`, `label`. Alternatively, you can download an example dataset:

````python
df = pd.read_csv('results.csv')  # should contain columns: task, worker, label
# df, ground_truth = load_dataset('relevance-2')  # or download an example dataset
````

Then, you can aggregate the workers' responses using the `fit_predict` method from the **scikit-learn** library:

````python
aggregated_labels = DawidSkene(n_iter=100).fit_predict(df)
````

[More usage examples](https://github.com/Toloka/crowd-kit/tree/main/examples)

## Implemented aggregation methods

Below is the list of currently implemented methods, including the already available (✅) and in progress (🟡).

### Categorical responses

| Method | Status |
| ------------- | :-------------: |
| [Majority Vote](reference/crowdkit.aggregation.classification.majority_vote.MajorityVote.md) | ✅ |
| [One-coin Dawid-Skene](reference/crowdkit.aggregation.classification.dawid_skene.OneCoinDawidSkene.md) | ✅ |
| [Dawid-Skene](reference/crowdkit.aggregation.classification.dawid_skene.DawidSkene.md) | ✅ |
| [Gold Majority Vote](reference/crowdkit.aggregation.classification.gold_majority_vote.GoldMajorityVote.md) | ✅ |
| [M-MSR](reference/crowdkit.aggregation.classification.m_msr.MMSR.md) | ✅ |
| [Wawa](reference/crowdkit.aggregation.classification.wawa.Wawa.md) | ✅ |
| [Zero-Based Skill](reference/crowdkit.aggregation.classification.zero_based_skill.ZeroBasedSkill.md) | ✅ |
| [GLAD](reference/crowdkit.aggregation.classification.glad.GLAD.md) | ✅ |
| [KOS](reference/crowdkit.aggregation.classification.kos.KOS.md) | ✅ |
| [MACE](reference/crowdkit.aggregation.classification.mace.MACE.md) | ✅ |
| BCC | 🟡 |

### Multi-label responses

|Method|Status|
|-|:-:|
|[Binary Relevance](reference/crowdkit.aggregation.multilabel.binary_relevance.BinaryRelevance.md)|✅|

### Textual responses

| Method | Status |
| ------------- | :-------------: |
| [RASA](reference/crowdkit.aggregation.embeddings.rasa.RASA.md) | ✅ |
| [HRRASA](reference/crowdkit.aggregation.embeddings.hrrasa.HRRASA.md) | ✅ |
| [ROVER](reference/crowdkit.aggregation.texts.rover.ROVER.md) | ✅ |

### Image segmentation

| Method | Status |
| ------------------ | :------------------: |
| [Segmentation MV](reference/crowdkit.aggregation.image_segmentation.segmentation_majority_vote.SegmentationMajorityVote.md) | ✅ |
| [Segmentation RASA](reference/crowdkit.aggregation.image_segmentation.segmentation_rasa.SegmentationRASA.md) | ✅ |
| [Segmentation EM](reference/crowdkit.aggregation.image_segmentation.segmentation_em.SegmentationEM.md) | ✅ |

### Pairwise comparisons

| Method | Status |
| -------------- | :---------------------: |
| [Bradley-Terry](reference/crowdkit.aggregation.pairwise.bradley_terry.BradleyTerry.md) | ✅ |
| [Noisy Bradley-Terry](reference/crowdkit.aggregation.pairwise.noisy_bt.NoisyBradleyTerry.md) | ✅ |

### Learning from crowds

|Method|Status|
|-|:-:|
|[CrowdLayer](reference/crowdkit.learning.crowd_layer.CrowdLayer.md)|✅|
|[CoNAL](reference/crowdkit.learning.conal.CoNAL.md)|✅|
|[TextSummarization](reference/crowdkit.learning.text_summarization.TextSummarization.md)|✅|

## Questions and bug reports

* To report a bug, post an issue on the [Toloka/bugreport](https://github.com/Toloka/crowd-kit/issues) page.
* To find answers to common questions or start a new discussion, join our English-speaking [Slack community]({{ toloka-slack }}).

## Source code

* [Crowd-Kit on GitHub](https://github.com/Toloka/crowd-kit)

{% include [global-community](../_includes/global-community.md) %}

{% include [social-media](../_includes/social-media.md) %}
