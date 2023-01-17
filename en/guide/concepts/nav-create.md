# Creating a skill

To create a skill:

1. Click {% if locale == "en-com" %}**+ Add skill**{% endif %} on the [Skills]({{ skills }}) page.

1. Enter the name of a new skill into the {% if locale == "en-com" %}**Title**{% endif %} field. The skill name should be short, clear and easy to distinguish from the names of other skills.

1. Describe the skill in the {% if locale == "en-com" %}**Description**{% endif %} field.

1. Choose the value of the {% if locale == "en-com" %}**Public?**{% endif %} option:

    - **No** — The default value. Tolokers will not be able to see the information about the skill.

    - **Yes** — Tolokers will see the name and the value of the assigned skill.

1. Click {% if locale == "en-com" %}**Add**{% endif %}.

{% note tip %}

To better motivate Tolokers, make the skill public and set [dynamic pricing](../../glossary.md#dynamic-pricing) based on this skill. In the task instructions, write what affects the skill value. Tolokers will know how the skill affects the price, and try to perform the tasks well.

{% endnote %}

## What's next {#what-next}

[Assign a skill](nav-assign.md) either manually or automatically.

## See also {#see-also}

- [{#T}](nav-use.md)
- [{#T}](nav-edit.md)
- [{#T}](nav-delete.md)
- [{#T}](filters.md)

## For developers {#for-developers}

- [Toloka API: Creating skill](../../api/concepts/create-skill.md)
- [Toloka-Kit: Creating skill](../../toloka-kit/reference/toloka.client.TolokaClient.create_skill.md)

## Troubleshooting {#troubleshooting}

{% include [faq-skill-for-every-pool](../_includes/faq/pool-setup/skill-for-every-pool.md) %}

{% include [faq-skill-for-different-projects](../_includes/faq/pool-setup/skill-for-different-projects.md) %}

{% include [troubleshooting-training](../_includes/troubleshooting/users/training.md) %}

{% include [contact-support](../_includes/contact-support.md) %}