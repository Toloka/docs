# Remove a skill

You can remove a skill only manually. It can't be done using quality control rules.

1. Go to the [Tolokers]({{ users }}) page.

1. Select the Tolokers to remove the skill from.

    {% include [select-tolokers](../_includes/select-tolokers.md) %}

1. Click {% if locale == "en-com" %}**-Skill**{% endif %}.

1. Select a skill.

1. Click {% if locale == "en-com" %}**Delete**{% endif %}.

## See also {#see-also}

- [{#T}](nav-create.md)
- [{#T}](nav-assign.md)
- [{#T}](nav-use.md)
- [{#T}](nav-edit.md)
- [{#T}](filters.md)

## For developers {#for-developers}

- [Toloka API: Removing skill from Toloker](../../api/concepts/delete-skill.md)
- [Toloka-Kit: Deleting Toloker skill](../../toloka-kit/reference/toloka.client.TolokaClient.delete_user_skill.md)

## Troubleshooting {#troubleshooting}

{% include [faq-skill-for-every-pool](../_includes/faq/pool-setup/skill-for-every-pool.md) %}

{% include [faq-skill-for-different-projects](../_includes/faq/pool-setup/skill-for-different-projects.md) %}

{% include [troubleshooting-training](../_includes/troubleshooting/users/training.md) %}

{% include [contact-support](../_includes/contact-support.md) %}