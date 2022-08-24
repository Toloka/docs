# History of skill changes

To download the history of skill changes:

1. Go to the [Tolokers]({{ users }}) page.
1. Select the Tolokers whose skill changes you want to view.

    #### How to select Tolokers
    {% if audience == "internal" %}
    {% note info %}

    The list may take several minutes to load. If you see **Tolokers not found**, try to wait a bit or use filters.

    {% endnote %}

    {% endif %}
    #### If you know the Toloker IDs

    To select one Toloker, enter their ID in the search field and click **Search**.

    To select multiple Tolokers:
    1. Create a text file and add the Toloker IDs in it, for example:
    ```
    059db2fa0927xec84a4cb9ccafc77ea4
    1a1f14bd48f0be13cb10c18sqgeb0679
    83khfalkdg78m3qhfai3kaf91h9n3ls3
    ```

    1. Click the {% if locale == "en-com" %}**Upload file**{% endif %} button at the bottom left and choose the file.
    1. When the file is uploaded, click {% if locale == "en-com" %}**Add**{% endif %}.

    {% note info %}

    To view detailed information about a Toloker, click on their ID.

    {% endnote %}

    #### Show blocked users

    By default, blocked users aren't displayed. Click the drop-down list for other options:
    - **Project ban** — Tolokers you blocked in one of the project pools, for example based on a quality control rule.
    - **Requester ban** — Tolokers you blocked in all your projects.
    - **Blocked in the system** — Tolokers blocked in the platform for violating the rules, poor response quality, or frequent errors when entering captcha.
    - **All** — Show both blocked and not blocked users.
    ![](../_images/other/users-ban-filter.png)
    #### Exclude those who haven't used Toloka for a long time.
    Choose **Show active users** and specify the number of days when the Toloker completed at least one task.
    #### Find those who opened or completed my tasks

    **In the left part of the window** use the **Project** and **Pool** fields to select Tolokers who opened tasks in one of your projects or pools.

    On the pool statistics page, these Tolokers are listed in the **Interested in pool** field.

    The **Completed** field shows the number of completed tasks. If the number is `0`, it means the Toloker only opened a task but didn't complete it.

    #### Find Tolokers with a skill

    To find Tolokers by skill, use [filters](../../glossary.md#filtering-ru):

    1. Click **Add filter**.
    1. Scroll down and choose **Choose skill**.
    1. Specify the skill and the required skill value.

    Filters for selecting Tolokers work the same way as in the pool. Learn more in the [Filters](filters.md) section.

1. Hover over the skill line and click ![](../_images/download.svg).

1. Open the downloaded file and choose a pipe `|` as a separator. The file may contain the following fields:

    - `worker_id` — Toloker ID.
    - `pool_id` — ID of the pool where the skill is used as a [filter](../../glossary.md#filtering-ru) or in a [quality control rule](../../glossary.md#quality-control-ru). If the value is empty, it means that the skill was assigned to the Toloker manually.
    - `skill_id` — Skill ID.
    - `skill_name` — Skill name.
    - `value` — Skill value.
    - `created_date` — Date the skill was created.
    - `action` — Action: `CREATE`/`MODIFY`.
    - `message` — Message.

    The file contains the skill change history for the last three months.


To view statistics about use of a skill, select it on the [Skills]({{ skills }}) page.


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
