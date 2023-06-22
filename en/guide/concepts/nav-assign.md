# Assigning the skill

You can assign a skill to Tolokers either manually or automatically: using quality control rules or after training.

## Using quality control rules {#rules}

The quality control rules feature the following actions:

- **Assign skill value** — Set a fixed skill value. This option is available in most [quality control rules](control.md).

    You decide what value to set and what it means. If the value is irrelevant, you can set any number, such as `1` or `42`.

    For example, in the [Submitted responses](submitted-answers.md) rule, you can assign the “Experienced” skill to the Toloker if they completed more than 20 assignments. You can set any skill value. Tolokers with the “Experienced” skill can be granted access to more complex tasks. To do this, just specify **Experienced ≠ Missing** in the filters of the pool with more complex tasks.

- **Assign skill from the field** — Set a value calculated automatically, for example, the percentage of the Toloker's correct [task responses](../../glossary.md#task-response).

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

1. Click **+Skill**.

1. Choose a skill and specify the skill value. If there is no skill, create it.

1. Click **Save**.

## What's next {#what-next}

[Use the skill](nav-use.md), for example, to select Tolokers or manage overlap or price.

## See also {#see-also}

- [{#T}](nav-create.md)
- [{#T}](nav-edit.md)
- [{#T}](nav-delete.md)
- [{#T}](filters.md)

## For developers {#for-developers}

- [Toloka API: Setting skill value](https://toloka.ai/docs/api/api-reference/#put-/user-skills)
- [Toloka-Kit recipe: Assign skill to Toloker](../../toloka-kit/recipes/assign-skill.md)

## Troubleshooting {#troubleshooting}

{% include [faq-skill-for-every-pool](../_includes/faq/pool-setup/skill-for-every-pool.md) %}

{% include [faq-skill-for-different-projects](../_includes/faq/pool-setup/skill-for-different-projects.md) %}

{% include [troubleshooting-training](../_includes/troubleshooting/users/training.md) %}

{% include [contact-support](../_includes/contact-support.md) %}