# History of skill changes

To download the history of skill changes:

1. Go to the [Tolokers]({{ users }}) page.

1. Select the Tolokers whose skill changes you want to view.

   {% include [select-tolokers](../_includes/select-tolokers.md) %}

1. Click on the Toloker's ID to view detailed information.

1. Hover over the skill line and click ![](../_images/download.svg).

1. Open the downloaded file and choose a pipe `|` as a separator. The file may contain the following fields:

    - `worker_id` — Toloker ID.
    - `pool_id` — ID of the pool where the skill is used as a [filter](../../glossary.md#filters) or in a [quality control rule](../../glossary.md#quality-control). If the value is empty, it means that the skill was assigned to the Toloker manually.
    - `skill_id` — Skill ID.
    - `skill_name` — Skill name.
    - `value` — Skill value.
    - `created_date` — Date the skill was created.
    - `action` — Action: `CREATE`/`MODIFY`.
    - `message` — Message.

    The file contains the skill change history for the last three months.

To view statistics about skill usage, select it on the [Skills]({{ skills }}) page.

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