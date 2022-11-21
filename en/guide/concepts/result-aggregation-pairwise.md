# Side-by-side comparison

We recommend using aggregation for tasks with an [overlap](../glossary.md#overlap) of 2 or higher. Learn more about this process in [Aggregation of results](result-aggregation.md).

The available aggregation algorithms include side-by-side comparison methods:

## Bradley-Terry aggregation model {#bradley-terry}

The Bradley-Terry aggregation model is a probabilistic model that can predict the result of side-by-side comparison.
      
### How it works

The algorithm evaluates objects based on side-by-side comparison.

Let's say we have two objects: `i` and `j`. The formula for calculating the probability that object `i` is rated higher than `j` is as follows:

![](../_images/results/bradley-terry-formula.svg)

where `p[i]` is a positive real parameter assigned to object `i`. For example, the `p[i]` parameter can be the value of the indicator against which objects are compared.

Based on all comparisons, the algorithm makes a complete rating of objects.

{% note info %}

Aggregation only includes accepted tasks.

{% endnote %}

## NoisyBT aggregation method {#noisyBT}

The noisyBT method is a modification of the [Bradley-Terry model](#bradley-terry) that takes Toloker parameters into account.

This method is based on the assumption that the contribution of each Toloker to the result of side-by-side comparison is different. This method evaluates and takes the skill of each Toloker into account.

## Troubleshooting

{% cut "Where do I see the aggregation progress?" %}

The pool page contains the {% if locale == "en-com" %}**List of Operations**{% endif %} button.

{% endcut %}

{% cut "Can I get notifications when results aggregation finishes?" %}

Yes. To set up notifications in your account, go to **Profile → Notifications → Pool or aggregation completed**. Learn more about [setting up notifications](../concepts/result-aggregation.md).

{% endcut %}

{% include [contact-support](../_includes/contact-support-help.md) %}