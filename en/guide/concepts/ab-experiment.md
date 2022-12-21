# Using A/B experiments

A/B testing is a method of user experience research. It includes statistical testing of hypotheses and choosing the most appropriate option from multiple ones.

## When to use {#usage}

Use A/B experiments to:

- Find out how changes in the [instructions](instruction.md), [interface](../../template-builder/quickstart.md#interface), [filters](../../glossary.md#filters), or in the [quality control rules](../../glossary.md#quality-control-rule) affect the Tolokers responses.

- Launch the [pools](../../glossary.md#pool) or the [projects](../../glossary.md#project) with different settings for independent groups of Tolokers.

- Control the labeling quality. If your pool is small, it's hard to track how Toloker's labeling quality changes over time. For example, the Toloker had passed the exam but then for some reason their performance got worse. The experiments allow you to filter out such Tolokers even if your pool has few tasks.

## How it works {#how-it-works}

- Each Toloker has an `id` number ranging from 1 to 100 (100 independent groups of Tolokers). Parameter is set to a Toloker like a [skill](../../glossary.md#skill) and Tolokers will always be placed into the the same group.

- Use the **Experiment group (1-100)** filter in the pool settings to select Tolokers from one or several groups.

- To create an A/B experiment add two pools with different values of the **Experiment group (1-100)** filter.

![](../_images/other/ab-experiment.png =700x)

{% note alert %}

Use the **Experiment group (1-100)** filter carefully. If you set the **Experiment group (1-100)** filter `= 1` in one pool and **Experiment group (1-100)** filter `= 2` in another pool, then about 98% of the Tolokers will not see your tasks.

{% endnote %}

## Troubleshooting {#troubleshooting}

{% cut "Can I select two filters at once?" %}

Yes. For example, if you set the **Experiment group (1-100)** `= 1` and **Languages** `= English`, you will get all the Tolokers with `id` number equal to `1` who speak English.

{% endcut %}

{% cut "Can I run the experiments within one project?" %}

Yes. To run A/B experiments within one project, it must have two pools with different values of the **Experiment group (1-100)** filter.

{% endcut %}

{% cut "Can part of the Tolokers do tasks from both pools?" %}

Yes, if there is an intersection of the values in the **Experiment group (1-100)** filter (for example, `≥ 40` in one pool and `≤ 60` in the other pool, in this case the Tolokers with the IDs from 40 to 60 will be able to do tasks from both pools). Note that in this case the results of the experiment will be inaccurate.

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}