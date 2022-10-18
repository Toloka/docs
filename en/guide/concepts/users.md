# Viewing Tolokers

The [Tolokers]({{ users }}) page shows all Tolokers who opened at least one of your tasks. On this page, you can select Tolokers to:

- [Assign or take away a skill](nav.md).

- [Block or unblock access](ban.md). For example, if you blocked a Toloker by mistake.
- [Issue a reward](bonus.md) for good performance. Loyal Tolokers will complete your tasks more willingly.

#### How to select Tolokers
{% if audience == "internal" %}
{% note info %}

The list may take several minutes to load. If you see **Tolokers not found**, try to wait a bit or use filters.

{% endnote %}

{% endif %}

{% cut "If you know the Toloker IDs" %}

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

{% endcut %}

{% cut "Show blocked users" %}

By default, blocked users aren't displayed. Click the drop-down list for other options:
- **Project ban** — Tolokers you blocked in one of the project pools, for example based on a quality control rule.
- **Requester ban** — Tolokers you blocked in all your projects.
- **Blocked in the system** — Tolokers blocked in the platform for violating the rules, poor response quality, or frequent errors when entering captcha.
- **All** — Show both blocked and not blocked users.
![](../_images/other/users-ban-filter.png)
{% endcut %}

{% cut "Exclude those who haven't used Toloka for a long time." %}

Choose **Show active users** and specify the number of days when the Toloker completed at least one task.

{% endcut %}

{% cut "Find those who opened or completed my tasks" %}

**In the left part of the window** use the **Project** and **Pool** fields to select Tolokers who opened tasks in one of your projects or pools.

On the pool statistics page, these Tolokers are listed in the **Interested in pool** field.

The **Completed** field shows the number of completed tasks. If the number is `0`, it means the Toloker only opened a task but didn't complete it.

{% endcut %}

{% cut "Find Tolokers with a skill" %}

To find Tolokers by skill, use [filters](../../glossary.md#filtering-ru):

1. Click **Add filter**.
1. Scroll down and choose **Choose skill**.
1. Specify the skill and the required skill value.

Filters for selecting Tolokers work the same way as in the pool. Learn more in the [Filters](filters.md) section.

You can download the list of the chosen Tolokers. To do this, click **Download .xls** at the top right.

{% endcut %}


## Troubleshooting {#troubleshooting}

{% cut "Can I use a skill beyond a particular pool or project and apply it to other projects as well?" %}

Yes, of course — you can use the same skill for different projects. But most often, a skill is intended for a specific project. If the Toloker completes a certain task well, this doesn't mean that they will complete other ones successfully. Another disadvantage is that if you filter by skills that were set long ago, you will artificially limit the number of available Tolokers.

{% endcut %}

{% cut "More than 500 Tolokers passed the training, but the training skill shows only 30." %}

The pool shows the total number of Tolokers that completed at least one assignment. A training skill can be lost over time if you set repeated training in the pool settings. This setting allows a Toloker to pass the training again after a certain period if the Toloker didn't complete any tasks in associated pools or if there was a large time gap between completing tasks (for example, because of the [ban](../../glossary.md#banned-worker-ru)). The training skill displays the Tolokers who either recently completed training, or regularly complete your tasks so that the skill doesn't expire.

{% endcut %}

{% cut "How do I view information about Tolokers?" %}

You can view information about Tolokers of your tasks on the [Tolokers]({{ users }}) page. To view information about a Toloker, select their ID. The requester can access the following data in the Toloker profile: country and city, age, education, language skills. On the **Metainformation** tab, you can find the versions of the browser and operating system, the User-agent type, region detected by IP, and other Toloker parameters. To select the Tolokers for your [pool](../../glossary.md#pool-ru) based on their profile, device, geo location, and other parameters, use [filters](filters.md).

{% endcut %}

{% cut "Do you verify the information entered by the Toloker in the profile?" %}

It's the Toloker's responsibility to provide the information in the profile during registration. We don't request identity documents for registering in Toloka. If a profile seems suspicious to us, we ask the owner to confirm the information.

{% endcut %}

{% cut "Do Tolokers know their ID?" %}

No, only the requester can see the Toloker ID.

{% endcut %}

{% cut "Why can I filter Tolokers by gender in the pool settings, if gender isn't shown in the profile?" %}

The requester can't see the full details about specific Tolokers. For example, the requester can't see their date of birth, gender, last name, or first name. However, filters by date of birth and gender are available to the requester in the pool settings. You can use them to select a group of Tolokers without accessing the details about specific Tolokers. This decreases the risk of Toloker de-anonymization.

{% endcut %}

{% include [contact-support](../_includes/contact-support-help.md) %}
