# History of skill changes

To download the history of skill changes:

1. Go to the [Tolokers]({{ users }}) page.

1. Select the Tolokers whose skill changes you want to view.

   {% include [select-tolokers](../_includes/select-tolokers.md) %}

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

To view statistics about use of a skill, select it on the [Skills]({{ skills }}) page.

## Troubleshooting {#troubleshooting}

{% include [faq-skill-for-every-pool](../_includes/faq/pool-setup/skill-for-every-pool.md) %}

{% include [faq-skill-for-different-projects](../_includes/faq/pool-setup/skill-for-different-projects.md) %}

{% include [troubleshooting-training](../_includes/troubleshooting/users/training.md) %}

{% include [contact-support](../_includes/contact-support.md) %}