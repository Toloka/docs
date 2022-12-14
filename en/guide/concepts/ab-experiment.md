# Using A/B experiments

A/B testing is a method of user experience research. It includes statistical testing of hypotheses and choosing the most appropriate option from several.

## When to use {#usage}

Use A/B experiments to:

* Find out how changes in the instructions or in the interface of the [task](../../glossary.md#task) affect the responses of Tolokers.

* Control the markup quality. If your pool is small, it's hard to track how Toloker's markup quality changes over time. For example, the Toloker passed the exam but then for some reason his performance got worse. The experiments allow you to filter out such Tolokers even if your pool has few tasks.

## How it works {#how-it-works}

* Each Toloker has an `id` number ranging from 1 to 100 (100 independent groups of Tolokers). Parameter is set to a Toloker like a [skill](../../glossary.md#skill) and Tolokers will always be placed into the the same group.
* Use the **AB experiment** [filter](../../glossary.md#filters) in the [pool](../../glossary.md#pool) settings to select Tolokers from one or several groups.
* You can use the **AB experiment** filter to launch the pools or the projects with different settings on independent groups of Tolokers.
* To create an A/B experiment add two pools with different values of the **AB experiment** filter.

{% note alert %}

Use the **AB experiment** filter carefully. If you set the **AB experiment** filter `= 1` in one pool and **AB experiment** filter `= 2` in another pool, then about 98% of the Tolokers will not see your tasks.

{% endnote %}

## Troubleshooting {#troubleshooting}

{% cut "Can I select two filters at once?" %}

Yes. For example, if you set the **AB experiment** `= 1` and **Languages** `=` **English**, you will get all the Tolokers with `id` number equals `1` who speak English.

{% endcut %}

{% cut "Can I do the experiments within one project?" %}

Yes. To do A/B experiments within one project, it must have two pools with different values of the **AB experiment** filter.

{% endcut %}

{% cut "Can part of the Tolokers perform tasks from both pools?" %}

Yes, if you select more than 50 `id` values in the **AB experiment** filter for each pool. Note that in this case the results of the experiment will be inaccurate.

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}