# Assigning the skill

You can assign a skill to Tolokers either manually or automatically: using quality control rules or after training.

## Using quality control rules {#rules}

The quality control rules feature the following actions:

- **Assign skill value** — Set a fixed skill value. This option is available in most [quality control rules](control.md).

    You decide what value to set and what it means. If the value is irrelevant, you can set any number, such as `1` or `42`.

    For example, in the [Submitted responses](submitted-answers.md) rule, you can assign the “Experienced” skill to the Toloker if they completed more than 20 assignments. You can set any skill value. Tolokers with the “Experienced” skill can be granted access to more complex tasks. To do this, just specify **Experienced ≠ Missing** in the filters of the pool with more complex tasks.

- **Assign skill from the field** — Set a value calculated automatically, for example, the percentage of the Toloker's correct responses.

    {% cut "Rules where this action is available" %}

    - [Control tasks](goldenset.md)
    - [Majority vote](mvote.md)
    - [Review results](reviewing-assignments.md)

    {% endcut %}

## After passing the training {#training}

After a Toloker passes a [training](../../glossary.md#training-pool) they are automatically assigned a [training skill](../../glossary.md#training-skill) with the percentage of correct answers.

You don't need to create this skill, it is created when you add the first training pool. If a training has the **Retry after** setting on, the skill is also deleted automatically. [Learn more](train.md).

## Manually {#manual}

1. Go to the [Tolokers]({{ users }}) page.

1. Select the Tolokers to assign the skill to.

   {% include [select-tolokers](../_includes/select-tolokers.md) %}

1. Click {% if locale == "en-com" %}**+Skill**{% endif %}.

1. Choose a skill and specify the skill value. If there is no skill, create it.

1. Click {% if locale == "en-com" %}**Save**{% endif %}.

## What's next {#what-next}

[Use the skill](nav-use.md), for example, to select Tolokers or manage overlap or price.

## Troubleshooting {#troubleshooting}

{% cut "Should I create a skill for every pool?" %}

It is better to use one [skill](../../glossary.md#skill) in a project. You can choose the way to calculate the skill:

- Calculate the skill for each pool separately. The current skill value is the value of the skill in the pool the Toloker completed last. This option is convenient if:

    - The pools are intended for different groups of Tolokers (for example, there are filters by city or country).

    - Pools are started one by one and you don't want to take into account the responses in the previous pools to calculate the skill in the current pool.

    This calculation method is used by default when adding a quality control rule to a pool. For the control tasks block, leave the **Recent control task responses to use** field empty.

- Calculate skill based on all tasks in a project This option is good if the pools are small and you don't need to have skill calculated for each pool.

    This option is available only for skills on control tasks. To use it, fill in the **Recent control task responses to use** field in pool quality control rules.

{% endcut %}

{% cut "Can I use a skill beyond a particular pool or project and apply it to other projects as well?" %}

Yes, of course — you can use the same skill for different projects. But most often, a skill is intended for a specific project. If the Toloker completes a certain task well, this doesn't mean that they will complete other ones successfully. Another disadvantage is that if you filter by skills that were set long ago, you will artificially limit the number of available Tolokers.

{% endcut %}

{% cut "More than 500 Tolokers passed the training, but the training skill shows only 30." %}

The pool shows the total number of Tolokers that completed at least one assignment. A training skill can be lost over time if you set repeated training in the pool settings. This setting allows a Toloker to pass the training again after a certain period if the Toloker didn't complete any tasks in associated pools or if there was a large time gap between completing tasks (for example, because of the [ban](../../glossary.md#banning-tolokers)). The training skill displays the Tolokers who either recently completed training, or regularly complete your tasks so that the skill doesn't expire.

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}