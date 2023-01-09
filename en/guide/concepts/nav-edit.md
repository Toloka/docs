# Editing a skill

You can both edit the skill itself and change the skill values for a specific Toloker.

## Changing the skill value for a Toloker {#value-edit}

1. Go to the [Tolokers]({{ users }}) page.

1. Select the Tolokers to change the skill value for.

   {% include [select-tolokers](../_includes/select-tolokers.md) %}

1. Hover over the skill line and click ![](../_images/edit.svg).

1. Enter the new skill value.

1. Click {% if locale == "en-com" %}**Save**{% endif %}.

## Editing the skill parameters {#reward-edit}

1. Open the **Skills** page.

1. Hover the cursor over the desired skill and click ![](../_images/edit.svg).

1. Change the skill name, type, or description and click **Save**.

## See also {#see-also}

- [{#T}](nav-create.md)
- [{#T}](nav-assign.md)
- [{#T}](nav-use.md)
- [{#T}](nav-delete.md)
- [{#T}](filters.md)

## For developers {#for-developers}

- [Toloka API: Setting skill value](../../api/concepts/set-skill.md)
- [Toloka API: Editing skill](../../api/concepts/edit-skill.md)
- [Toloka-Kit: Setting user skill](../../toloka-kit/reference/toloka.client.TolokaClient.set_user_skill.md)
- [Toloka-Kit: Updating user skill](../../toloka-kit/reference/toloka.client.TolokaClient.update_skill.md)

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

{% include [troubleshooting-training](../_includes/troubleshooting/users/training.md) %}

{% include [contact-support](../_includes/contact-support.md) %}