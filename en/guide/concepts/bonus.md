# Rewards

To motivate Tolokers to complete your project tasks quickly and provide high-quality responses, you can give extra rewards for individual tasks, or reward one or more trusted users (in addition to paying them for [task completion](../../glossary.md#completed-tasks)).

The reward amount can be from $0.005 to $100 per Toloker per time.

A [fee](budget.md) also applies to rewards.

## For a task {#bonus-task}

This is the recommended method, since it is the most economical and targeted for motivating Tolokers.

To issue a reward for a specific pool task, use [online task review](accept.md#acception):

1. Click the {% if locale == "en-com" %}**Review assignments**{% endif %} button on the pool page.

1. Choose a task and open it. Please note that a reward can only be issued for an accepted task.

1. Click {% if locale == "en-com" %}**Actions → Issue bonus**{% endif %}

    {% cut "Example" %}

    ![](../_images/bonus/bonus-task-1.png)

    {% endcut %}

1. Fill in the fields in the {% if locale == "en-com" %}**Issue bonus**{% endif %} window that appears:

    - {% if locale == "en-com" %}**Bonus per user**{% endif %} in dollars.

    - {% if locale == "en-com" %}**Topic**{% endif %} and {% if locale == "en-com" %}**Message**{% endif %} for Tolokers. Specify what exactly the reward is credited for. To send messages in different languages, use the button for switching languages.

    {% cut "Example" %}

    ![](../_images/bonus/bonus-task-2.png)

    {% endcut %}

1. Click {% if locale == "en-com" %}**Grant**{% endif %}.

## Selected Tolokers {#bonus-selected-annotators}

To issue rewards to Tolokers:

1. Go to the [Tolokers]({{ users }}) page.

1. Choose the Tolokers who will receive the reward.

    {% cut "How to select Tolokers" %}

    {% include [select-tolokers-internal](../_includes/select-tolokers-internal.md) %}

    {% endcut %}

1. Specify the [project](../../glossary.md#project) or [pool](../../glossary.md#pool) in the corresponding fields in the left part of the page.

    {% cut "Example" %}

    ![](../_images/bonus/bonus-one-performer-2.png)

    {% endcut %}

1. To credit rewards to one Toloker, click the link to their ID in the {% if locale == "en-com" %}**Toloker ID**{% endif %} field.

    On the page that opens, click {% if locale == "en-com" %}**Actions → Issue bonus**{% endif %}.

    To credit rewards to a group of Tolokers click {% if locale == "en-com" %}**Issue bonus**{% endif %}.

1. Fill in the fields in the {% if locale == "en-com" %}**Issue bonus**{% endif %} window that appears:

    - {% if locale == "en-com" %}**Bonus per Toloker**{% endif %} in dollars.

    - {% if locale == "en-com" %}**Topic**{% endif %} and {% if locale == "en-com" %}**Message**{% endif %} for Tolokers. Specify the projects and accomplishments the reward was granted for. To send messages in different languages, use the button for switching languages.

1. Click {% if locale == "en-com" %}**Grant**{% endif %}.

    Before doing this, check the number of people who will receive the reward, and the total amount.

    {% cut "Example" %}

    ![](../_images/bonus/bonus-group-performers-1.png)

    {% endcut %}

The Toloker will see rewards for completed tasks, activity and quality of work in projects in their profile (the {% if locale == "en-com" %}**History**{% endif %} tab). The transferred amounts are added to the list of payments.

{% cut "Example" %}

![](../_images/bonus/bonus-task-3.png)

{% endcut %}

You can track money deducted for extra rewards in your [profile]({{ profile }}) on the {% if locale == "en-com" %}**Spent**{% endif %} tab.

## Troubleshooting {#troubleshooting}

{% cut "How do I reward Tolokers in addition to the basic task price?" %}

You can increase the basic task price for Tolokers that have a higher skill. To do this, set up [Dynamic pricing](dynamic-pricing.md). If you want to motivate high-quality Tolokers regardless of their skill, use [rewards](../troubleshooting/users.md). In your task instructions, specify the amount and conditions for the Toloker rewards.

{% endcut %}

{% cut "How can I view statistics on paid rewards?" %}

To view your expenses that involve rewards, go to your [profile]({{ profile }}) and open the **Spent** tab.

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}
