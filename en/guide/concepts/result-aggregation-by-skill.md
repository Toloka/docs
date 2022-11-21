# Aggregation by skill

We recommend using aggregation for tasks with an [overlap](../glossary.md#overlap) of 2 or higher. Learn more about this process in [Aggregation of results](result-aggregation.md).

This method analyzes responses based on the level of confidence in the Toloker. The confidence level is determined by the skill you choose. Skills measure the probability of the Toloker completing the task correctly.

## Benefits

- If your project processes a large amount of data, the aggregation results will be more accurate compared to the Dawid-Skene method.
- You can choose the output data fields you want to aggregate.

## Features

Each user skill has "weight". The higher the skill, the more we trust the Toloker and believe that their responses are correct.

The result of aggregation is a file with responses. `CONFIDENCE: <field name [output](incoming.md)>` indicates the confidence in the aggregated response. In this case, it shows the probability that the response is correct.

{% cut "Example" %}

Tasks were labeled by three Tolokers with different "My skill" values: the first Toloker has a skill of 70, the second has 80, and the third has 90.

All three Tolokers responded to the first task with **OK**. In this case, we are 100% sure that **OK** is the correct response.

On the second task, the first and third Tolokers responded with **OK**, and the second Toloker responded with **BAD**. In this case, we'll compare the Tolokers' skills and determine the confidence based on the result.
            
## How it's calculated

Terms:

- $q[i]$is a Toloker's accuracy.
- $K$ — smoothing constant.
- $z[j]$is the most popular response.
- $z[x] estimate,$ — the probability that the estimate is correct.
                
A Toloker's accuracy $q[i]$ is calculated as follows:

$q[i] = \frac{K+correct.golden.sets[i]}{2×K+total.golden.sets[i]}$,

where:

$K$ is a smoothing constant (starting from 0.5) if there are not enough responses to control tasks.

If there are several estimates, the most popular response is determined by adding together $q[i]$ of the Tolokers who selected each response option. The response with the largest total is considered more correct. Let's call this estimate $z[j]$.
[Using Bayes' theorem](https://en.wikipedia.org/wiki/Bayes%27_theorem), we calculate the posterior probability that the estimate$z[j]$is correct.

A uniform distribution of estimates is assumed a priori. For the $z[x]$ estimate, the a priori probability is calculated as

$P(z[x]) = \frac{1}{Y}$,

where:

$Y$ is the number of response options.

Next, we calculate the probability that the estimate$z[j]$is correct.

If the Toloker responded$z[j]$, then the probability of this is equal to the Toloker's accuracy$q[i]$. If they responded differently, then the probability of this is:

$\frac{1-q[i]}{Y-1}$,

where:
$(1 - q[i])$is the remaining probability.
$(Y - 1)$is the number of remaining responses.

It ensures that the probability of an error is distributed evenly among the remaining estimates.

We take all Tolokers' responses and, for example, option$z[x] estimate,$and calculate the probability that Tolokers will select this response, provided that the correct response is$ z[x] estimate,$:

```
func z_prob(x int) : float {
  d = 1.0
  for w[i]: workers
       if answers[w[i]] == z[x]
          d *= q[i]
       else
          d *= (1 - q[i]) / (Y - 1)
  return d
}
```

Next, using Bayes' theorem, we calculate the probability that the response $z[j]$ is correct:

```                
r = 0
for z[i]: answer_options
  r += z_prob(i) * (1 / Y)

eps = z_prob(j) * (1 / Y) / r
```

{% note info %}

Aggregation only includes accepted tasks.

{% endnote %}

## Requirements

{% list tabs %}
- Pool with dynamic overlap

    To run aggregation, you must correctly set up dynamic overlap. To do this:

    1. Select a skill. We recommend to select a skill calculated as the percentage of [correct responses in control tasks](goldenset.md). This will give you the most accurate aggregation results.

    1. Select the output data fields.

    {% cut "Output data fields that can be aggregated" %}

    - Strings and numbers with allowed values.
      The allowed value must match the `value` parameter in the corresponding interface element.

    - Boolean.

    - Integers with minimum and maximum values. The maximum difference between them is 32.
      If there are too many possible responses in the output field, the dynamic overlap mechanism won't be able to aggregate the data.

    The allowed value must match the `value` parameter in the corresponding interface element.
    
    {% endcut %}

- Pools without dynamic overlap

You can run aggregation by skill if the pool meets the following requirements:

1. You set a skill that defines the level of confidence in the Toloker's responses. We recommend to use a skill calculated as the percentage of [correct responses in control tasks](goldenset.md).

1. The [output data fields](incoming.md) have allowed values.

{% cut "Output data fields that can be aggregated" %}

- Strings and numbers with allowed values.
  The allowed value must match the `value` parameter in the corresponding interface element.

- Boolean.

- Integers with minimum and maximum values. The maximum difference between them is 32.
  If there are too many possible responses in the output field, the dynamic overlap mechanism won't be able to aggregate the data.

The allowed value must match the `value` parameter in the corresponding interface element.

{% endcut %}

The tasks were uploaded in the pool with [smart mixing](distribute-tasks-by-pages.md#smart-mixing).

##Troubleshooting
    
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