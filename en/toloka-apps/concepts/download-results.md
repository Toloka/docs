# Downloading the results

{% note warning %}

You can only download the results from a batch with the **Completed** status.

{% endnote %}

## Download all results {#download-all}

1. Open your ready-to-go project and go to the appropriate batch.
1. Click **Download results** on the right.
1. Wait until the data export is completed.

## View the results by item {#objects}

1. Open your ready-to-go project and go to the appropriate batch. You'll see a list of labeled items.
1. Select an item and click on it. This opens a block of labeling results in JSON format.
1. Click **Copy** on the right. This adds the block with labeled data to the clipboard.

## Procedure of acceptance of services {#acceptance-procedure}

{% note info %}

In ready-to-go projects, only automatic acceptance is available. You can't reject responses manually.

{% endnote %}

All Tasks performed during the term specified in the Tasks shall be deemed automatically accepted by the Customer from the moment when every particular Task is completed by the User, and the Services shall be deemed duly provided by Toloka and subject to payment regardless of any other conditions. No discrepancy between results of the Task and the requirement set by Toloka in the Instruction shall constitute a basis for refusing to accept the relevant Services.

The result of labeling is a TSV file with responses. The `CONFIDENCE` field shows the level of confidence in a response. In this case, it shows the probability that the response is correct.

{% cut "Example" %}

Items were labeled by three performers with different levels of performance quality: the results of the first performer are slightly above average, the second is a good performer, and the third is an excellent performer.

All three performers responded to the first task with **OK**. In this case, we're 100% sure that **OK** is the correct response.

To the second task, the first and third performers responded with **OK**, and the second performer responded with **BAD**. In this case, we'll compare the performers' task completion quality and determine the confidence based on the result.

{% endcut %}

{% cut "How it's calculated" %}

Terms:

- $q[i]$ is a performer's accuracy.
- $K$ is a smoothing constant.
- $z[j]$ is the most popular response.
- $z[x]$ is the probability that the estimate is correct.

A performer's accuracy $q[i]$ is calculated as follows:

$q[i] = \frac{K+correct.golden.sets[i]}{2×K+total.golden.sets[i]}$,

where:

$K$ is a smoothing constant (starting from 0.5) if there are not enough responses to control tasks.

If there are several estimates, the most popular response is determined by adding together $q[i]$ of the performers who selected each response option. The response with the largest total is considered more correct. Let's call this estimate $z[j]$.

[Using Bayes' theorem](https://en.wikipedia.org/wiki/Bayes%27_theorem), we calculate the posterior probability that the estimate $z[j]$ is correct.

A uniform distribution of estimates is assumed a priori. For the $z[x]$ the a priori probability is calculated as

$P(z[x]) = \frac{1}{Y}$,

where:

$Y$ is the number of response options.

Next, we calculate the probability that the estimate $z[j]$ is correct.

If the performer responded $z[j]$, then the probability of this is equal to the performer's accuracy $q[i]$. If they responded differently, then the probability of this is:

$\frac{1-q[i]}{Y-1}$,

where:

$(1 - q[i])$ is the remaining probability.

It ensures that the probability of an error is distributed evenly among the remaining estimates.

We take all performers' responses and, for example, option $z[x]$ and calculate the probability that performers will select this response, provided that the correct response is $z[x]$:

```go
func z_prob(x int) : float {
    d = 1.0
    for w[i]: workers
         if answers[w[i]] == z[x]
            d *= q[i]
         else
            d *= (1 - q[i])
    return d
}
```

Next, using Bayes' theorem, we calculate the probability that the response $z[j]$ is correct:

```go
r = 0
for z[i]: answer_options
    r += z_prob(i) * (1 / Y)

eps = z_prob(j) * (1 / Y) / r
```

{% endcut %}

## Troubleshooting {#troubleshooting}

{% cut "Why can't I download the results?" %}

The **Download results** button is only available for batches with the **Completed** status. Wait until the labeling is completed and return to the batch after a while.

{% endcut %}

{% cut "How do I find out how long it took to label my data?" %}

Select the desired batch. The section on the right will show all available statistics.

{% endcut %}

{% include [contact-support](_includes/contact-support.md) %}