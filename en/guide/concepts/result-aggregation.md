# Aggregation of results

If tasks were issued with an [overlap](../../glossary.md#overlap) of 2 or higher, run aggregation of results. Toloka will process all Tolokers' responses for the task and issue the resulting response and its confidence level.

![](../_images/results/aggregation-scheme.svg)

{% note info %}

If you run the [pool](../../glossary.md#pool) with the assignment review, make sure that all responses are [accepted](accept.md).

{% endnote %}

1. Open the [pool](pool-main.md).

1. Click ![Drop-down button](../_images/other/drop-down.svg) next to the {% if locale == "en-com" %}**Download results**{% endif %} button.

1. Choose the aggregation method:

    - [Dawid-Skene aggregation model](result-aggregation-dawid-skene.md)
    
    - [Aggregation by skill](result-aggregation-by-skill.md)
    
    - [Majority vote](result-aggregation-mv.md)
    
    - [Side-by-side comparison](result-aggregation-pairwise.md)
    
    - [Text aggregation](result-aggregation-text.md)

Aggregation takes from several minutes to several hours. Track the progress on the [Operations]({{ operations }}) page. When aggregation is complete, download the file with the results.

## Notifications {#notification}

To receive notifications and emails when results aggregation is completed, set up notifications:

1. Log in to your account.

1. Go to {% if locale == "en-com" %}**Profile → Notifications → Pool or aggregation completed**{% endif %}

1. Choose the notification method:

    - Email: Messages will be sent to your email address.

    - Messages: Notifications will be displayed under **Messages** in your account. Apart from you, those who set up [shared access](multiple-access.md) to your account can see them.

    - Browser: Notifications will be sent to the devices that you logged in to your account from.

## Troubleshooting {#troubleshooting}

{% cut "What is the difference between the confidence in the aggregated response in the Dawid-Skene aggregation model and the confidence in aggregation by skill?" %}

In the way it's calculated. In both aggregations, confidence means the same thing.

{% endcut %}

{% cut "How does the Dawid-Skene aggregation model work?" %}

The Dawid-Skene aggregation model analyzes the Toloker responses and creates a confusion matrix for each Toloker. This lets us evaluate the statistical significance of the Toloker in the context of each assignment. [Learn more about the model](https://www.jstor.org/stable/2346806).

{% endcut %}

{% cut "Why does the Dawid-Skene aggregation model return a result that the Tolokers didn't select?" %}

The method doesn't guarantee that original Toloker responses will be used for aggregation. The algorithm takes into account Tolokers' quality parameters and response patterns. Consequently, it can return a result that's different from the Tolokers' responses to this task.

{% endcut %}

{% cut "Where do I see the aggregation progress?" %}

The pool page contains the {% if locale == "en-com" %}**List of Operations**{% endif %} button.

{% endcut %}

{% cut "Why might aggregation by Toloker skill be unavailable?" %}

You cannot aggregate by project fields that have no valid values. Specify the possible values for all the fields of all types.

{% endcut %}

{% cut "You can't aggregate by skill. When running via the API, I get the error code `ONLY_FOR_POOL_WITH_MIXER`. Why?" %}

You need to use [smart mixing](distribute-tasks-by-pages.md#smart-mixing).

{% endcut %}

{% include [contact-support](../_includes/contact-support-help.md) %}