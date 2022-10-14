# Creating a skill

To create a skill, click {% if locale == "en-com" %}**+Add skill**{% endif %} on the [Skills]({{ skills }}) page.

If you make a skill public, Tolokers can see information about the assigned skill: name and value.

{% note info %}

To better motivate Tolokers, make the skill public and set [dynamic pricing](../../glossary.md#dynamic-pricing-ru) based on this skill. In the task instructions, write what affects the skill value. Tolokers will know how the skill affects the price, and try to perform the tasks well.

{% endnote %}

## What's next {#what-next}

[Assign a skill](nav-assign.md) either manually or automatically.


## Troubleshooting {#troubleshooting}

#### Should I create a skill for every pool?

It is better to use one [skill](../../glossary.md#skill-ru) in a project. You can choose the way to calculate the skill:

- Calculate the skill for each pool separately. The current skill value is the value of the skill in the pool the Toloker completed last. This option is convenient if:

    - The pools are intended for different groups of Tolokers (for example, there are filters by city or country).

    - Pools are started one by one and you don't want to take into account the responses in the previous pools to calculate the skill in the current pool.

    This calculation method is used by default when adding a quality control rule to a pool. For the control tasks block, leave the **Recent control task responses to use** field empty.

- Calculate skill based on all tasks in a project This option is good if the pools are small and you don't need to have skill calculated for each pool.

    This option is available only for skills on control tasks. To use it, fill in the **Recent control task responses to use** field in pool quality control rules.


#### Can I use a skill beyond a particular pool or project and apply it to other projects as well?

Yes, of course — you can use the same skill for different projects. But most often, a skill is intended for a specific project. If the Toloker completes a certain task well, this doesn't mean that they will complete other ones successfully. Another disadvantage is that if you filter by skills that were set long ago, you will artificially limit the number of available Tolokers.

#### More than 500 Tolokers passed the training, but the training skill shows only 30.

The pool shows the total number of Tolokers that completed at least one assignment. A training skill can be lost over time if you set repeated training in the pool settings. This setting allows a Toloker to pass the training again after a certain period if the Toloker didn't complete any tasks in associated pools or if there was a large time gap between completing tasks (for example, because of the [ban](../../glossary.md#banned-worker-ru)). The training skill displays the Tolokers who either recently completed training, or regularly complete your tasks so that the skill doesn't expire.


{% include [contact-support](../_includes/contact-support-help.md) %}
