# Dawid-Skene model

The Dawid-Skene aggregation model [aggregates](result-aggregation.md) responses taking into account the heterogeneity of Tolokers. [Statistical significance](https://en.wikipedia.org/wiki/Statistical_significance) of the resulting response is determined based on the analysis of all Tolokers' responses.

## How it works

The model evaluates `|L|²` parameters for each Toloker, where `L` is the number of all unique aggregation values.

The parameters used by the model are determined automatically for each pool and are only used in calculations. You won't see these parameters in the aggregated results.

{% note info %}

Because the Dawid-Skene model evaluates `|L|²` parameters for each Toloker, we don't recommend using it when the Toloker labels `< |L|²` tasks. Otherwise, the quality of aggregation may be poor.

{% endnote %}

The result of aggregation is a file with responses. `CONFIDENCE: <field name [output](incoming.md)>` indicates the response significance as a percentage.

## Benefits

Data for aggregation can be uploaded any way you want.

## Features

The Dawid-Skene model is a non-trivial aggregation algorithm. Check out its features and learn more [about the model](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.469.1377&amp;rep=rep1&amp;type=pdf).

- The method doesn't guarantee that original Toloker responses will be used for aggregation. The algorithm takes into account Tolokers' quality parameters and response patterns. Consequently, it can produce a result that's different from the Tolokers' responses to this task.

{% cut "Example" %}

In an image classification task, all three Tolokers selected the first response option. In another similar task, the same three Tolokers selected the first option, and the fourth Toloker selected the second option. If in the next task, the only response is given by the fourth Toloker, the Dawid-Skene aggregation model might consider it incorrect and return a different result.

{% endcut %}

- The Dawid-Skene aggregation model works with [control](../glossary.md#control-task) and [training](../glossary.md#training-task) tasks as well as with general tasks. There is a possibility that the `OUTPUT:result` field for the control task in the file with the results won't match the actual response to this task (`GOLDEN:result`).

- If your project has output data marked as `"required": false` and Tolokers don't fill in this field, it won't be included in aggregation. For example, you have 1000 tasks. In 999 of them, Tolokers didn't label the `label` field, and one Toloker labeled it as `label=x`. As a result of aggregation, this data field will have `CONFIDENCE = 100%`, since only one task out of a thousand falls under the aggregation conditions.

{% cut "How it's calculated" %}

The Dawid-Skene method puts together an [confusion matrix](https://en.wikipedia.org/wiki/Confusion_matrix) and response popularity for each Toloker. It uses the [EM algorithm](https://en.wikipedia.org/wiki/Expectation–maximization_algorithm).

The idea is that it collects the most accurate aggregated responses for each task, recording the confusion matrices and response popularity. It aims to determine the best popularities and confusion matrices among all responses. The process has several stages. Initially, the majority opinion is used to confirm that the response is correct.

[Description of the Dawid-Skene method](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.469.1377&amp;rep=rep1&amp;type=pdf).

If you want to learn how the Dawid-Skene method is implemented in Toloka, check out the [Crowd-Kit documentation](https://toloka.ai/docs/crowd-kit/reference/crowdkit.aggregation.classification.dawid_skene.DawidSkene.html).

{% endcut %}

{% note info %}

Aggregation only includes accepted tasks.

{% endnote %}

## Requirements

The main requirement for this aggregation is the output data fields:

{% list tabs %}

- Fields that can be aggregated

    - Strings and numbers with allowed values. The allowed value must match the `value` parameter in the corresponding interface element.

    - Boolean.

    - Integers with minimum and maximum values. The maximum difference between them is 32. If there are too many possible responses in the output field, the dynamic overlap mechanism won't be able to aggregate the data.

    The allowed value must match the `value` parameter in the corresponding interface element.

- Fields that can't be aggregated

    - Array.
    - File.
    - Coordinates.
    - JSON object.

{% endlist %}

## How do I check it?

If you have doubts that the Dawid-Skene aggregation model works correctly, you can:

- Reassign tasks and compare the results.
- Check the task manually.

## Troubleshooting
    
{% cut "What is the difference between the confidence in the aggregated response in the Dawid-Skene aggregation model and the confidence in aggregation by skill?" %}

In the way it's calculated. In both aggregations, confidence means the same thing.

{% endcut %}

{% cut "How does the Dawid-Skene aggregation model work?" %}

The Dawid-Skene aggregation model analyzes the Toloker responses and creates an confusion matrix for each Toloker. This lets us evaluate the statistical significance of the Toloker in the context of each assignment. [Learn more about the model](https://www.jstor.org/stable/2346806).

{% endcut %}

{% cut "Why does the Dawid-Skene aggregation model return a result that the Tolokers didn't select?" %}

The method doesn't guarantee that original Toloker responses will be used for aggregation. The algorithm takes into account Tolokers' quality parameters and response patterns. Consequently, it can return a result that's different from the Tolokers' responses to this task.

{% endcut %}

{% cut "Where do I see the aggregation progress?" %}

The pool page contains the **List of Operations** button.

{% endcut %}

{% cut "Why might aggregation by Toloker skill be unavailable?" %}

You cannot aggregate by project fields that have no valid values. Specify the possible values for all the fields of all types.

{% endcut %}

{% cut "You can't aggregate by skill. When running via the API, I get the error code `ONLY_FOR_POOL_WITH_MIXER`. Why?" %}

You need to use [smart mixing](../concepts/distribute-tasks-by-pages.md#smart-mixing).

{% endcut %}

{% include [contact-support](../_includes/contact-support-help.md) %}