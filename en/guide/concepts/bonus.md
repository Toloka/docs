# Rewards

To motivate Tolokers to complete your project tasks quickly and provide high-quality responses, you can give extra rewards for individual tasks, or reward one or more trusted users (in addition to paying them for [task completion](../../glossary.md#submitted-answers-ru)).

The reward amount can be from 0.01 to 100 dollars per Toloker per time.

A [fee](budget.md) also applies to rewards.

## For a task {#bonus-task}

This is the recommended method, since it is the most economical and targeted for motivating Tolokers.

To issue a reward for a specific pool task, use [online task review](accept.md#acception):

1. Click the {% if locale == "en-com" %}**Review assignments**{% endif %} button on the pool page.

1. Choose a task and open it. Please note that a reward can only be issued for an accepted task.

1. Click {% if locale == "en-com" %}{% endif %}
    #### Example
    ![](../_images/bonus/bonus-task-1.png)

1. Fill in the fields in the {% if locale == "en-com" %}**Issue bonus**{% endif %} window that appears:

    - {% if locale == "en-com" %}**Bonus per user**{% endif %} in dollars.

    - {% if locale == "en-com" %}**Topic**{% endif %} and {% if locale == "en-com" %}**Message**{% endif %} for Tolokers. Specify what exactly the reward is credited for. To send messages in different languages, use the button for switching languages.

    #### Example
    ![](../_images/bonus/bonus-task-2.png)

1. Click {% if locale == "en-com" %}**Grant**{% endif %}.


## Selected Tolokers {#bonus-selected-annotators}

To issue rewards to Tolokers:

1. Go to the [Tolokers]({{ users }}) page.

1. Choose the Tolokers who will receive the reward.

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

1. Specify the [project](../../glossary.md#project-ru) or [pool](../../glossary.md#pool-ru) in the corresponding fields in the left part of the page.

    #### Example
    ![](../_images/bonus/bonus-one-performer-2.png)

1. To credit rewards to one Toloker, click the link to their ID in the {% if locale == "en-com" %}**Toloker ID**{% endif %} field.

    On the page that opens, click {% if locale == "en-com" %}{% endif %}.

    To credit rewards to a group of Tolokers click {% if locale == "en-com" %}**Issue bonus**{% endif %}.

1. Fill in the fields in the {% if locale == "en-com" %}**Issue bonus**{% endif %} window that appears:

    - {% if locale == "en-com" %}**Bonus per Toloker**{% endif %} in dollars.

    - {% if locale == "en-com" %}**Topic**{% endif %} and {% if locale == "en-com" %}**Message**{% endif %} for Tolokers. Specify the projects and accomplishments the reward was granted for. To send messages in different languages, use the button for switching languages.

1. Click {% if locale == "en-com" %}**Grant**{% endif %}.

    Before doing this, check the number of people who will receive the reward, and the total amount.

    #### Example
    ![](../_images/bonus/bonus-group-performers-1.png)


The Toloker will see rewards for completed tasks, activity and quality of work in projects in their profile (the {% if locale == "en-com" %}**History**{% endif %} tab). The transferred amounts are added to the list of payments.

#### Example
![](../_images/bonus/bonus-task-3.png)

You can track money deducted for extra rewards in your [profile]({{ profile }}) on the {% if locale == "en-com" %}**Expenses**{% endif %} tab.


## Troubleshooting {#troubleshooting}

#### How do I reward Tolokers in addition to the basic task price?

You can increase the basic task price for Tolokers that have a higher skill. To do this, set up [Dynamic pricing](dynamic-pricing.md). If you want to motivate high-quality Tolokers regardless of their skill, use [rewards](../troubleshooting/users.md). In your task instructions, specify the amount and conditions for the Toloker rewards.

#### How can I view statistics on paid rewards?

To view your expenses that involve rewards, go to your [profile]({{ profile }}) and open the **Expenses** tab.

{% include [contact-support](../_includes/contact-support-help.md) %}