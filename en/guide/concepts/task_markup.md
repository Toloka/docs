# Task markup

{% note alert "Restriction" %}

Task markup is available only for [training pools](train.md) and pools uploaded with [“smart mixing”](distribute-tasks-by-pages.md#smart-mixing).

{% endnote %}

Using markup, you can add correct responses and hints to tasks, as well as change task types. You can turn a general task into a [control task](../../glossary.md#control-task) by adding the correct answer, or into a [training task](../../glossary.md#training-task) by adding the correct answer and a hint.

{% cut "Why this is important" %}

Using control tasks, you can track Tolokers' task completion quality: assign skills, select Tolokers for projects, configure dynamic overlap, and set up pricing.

Tolokers' task completion quality may be low in the following cases:

- There are no control tasks in the pool. As a result, dishonest Tolokers and Tolokers with low labeling skill levels may participate in the project.

- Control tasks in the pool are not updated regularly. As a result, Tolokers can guess correct answers, which makes the effectiveness of quality control decrease.

{% endcut %}

There are two ways to create control tasks:

- [Automatic markup](#auto-markup) by Toloka experts.

- [Manual markup](task-markup-by-yourself.md), which allows you to create both control tasks and training tasks.

## How to set up automatic markup {#auto-markup}

To save time, you can opt for having your control tasks edited by Toloka experts. In this case, markup is performed within the pool.

You can set up automatic markup if the following conditions are met:

- Markup is only available for [control tasks](../../glossary.md#control-task).

- By default, markup is supported for object classification projects created with the following templates:

    - **Image classification**
    - **Hand gesture classification**
    - **Clickbait or not?**
    - **Sentiment analysis & Content moderation**
    - **Product search relevance**

- For other types of projects, you can request this feature by contacting [support](#toloka-support).

- The pool must contain more than 100 tasks.

- At least one required output field must be set up in the task interface.

- You can get control tasks only once for each project. This does not apply to cases when task markup failed.

- Control task markup performed by Toloka is only available in the interface. You can't access this feature through the API.

## How does it work? {#how-work}

{% note alert %}

Don't make changes to the project or pool while tasks are being edited. Markup will continue without these changes taken into account, which may result in discrepancies.

{% endnote %}

1. Make sure the pool isn't running.

1. Make sure that the task instructions are correct.

1. Click {% if locale == "en-com" %}**Edit**{% endif %} in the {% if locale == "en-com" %}**Pool tasks**{% endif %} section.

1. Go to the {% if locale == "en-com" %}**General**{% endif %} tab.

1. In the {% if locale == "en-com" %}**We can label control tasks for you**{% endif %} section, click {% if locale == "en-com" %}**Try it for free**{% endif %}.

1. Click {% if locale == "en-com" %}**Order**{% endif %}. Your pool data will be sent for markup to expert Tolokers. For better quality, we use algorithms that select tasks that can be used as control tasks.

1. Wait until the markup is completed. This process usually takes about 6 hours. The estimated time of markup completion is indicated in the **Edit tasks** section.

1. After the markup is completed, the tasks are uploaded back to the pool. In the {% if locale == "en-com" %}**Edit tasks**{% endif %} section on the {% if locale == "en-com" %}**Control tasks**{% endif %} tab, you'll see the following message: “Control tasks are ready”. You can [edit](task-markup-by-yourself.md#task-edit) and [delete](task-markup-by-yourself.md#delete-task) the control tasks you received.

{% note info %}

If the markup process failed for some reason, contact support. Go to the tab for control tasks or to the pool page and click {% if locale == "en-com" %}**Contact us**{% endif %}. After the problem is solved, you'll be able to request control task markup again.

{% endnote %}

## What's next {#what_next}

- [Add a training pool](train.md).
- {% if locale == "en-com" %}[Top up your account](refill.md){% endif %}
- [Start the pool](pool-run-and-stop.md).

## Troubleshooting {#troubleshooting}

{% cut "How many control tasks do I need to add?" %}

We recommend adding at least 1% of control tasks in the pool. And for small pools — 5-10%.

{% cut "Why's that?" %}

Each control task is shown to the Toloker only once. If you use smart mixing, you determine how many control tasks should be in a suite. If each suite contains one control task, then the maximum number of suites the Toloker can complete is equal to the number of control tasks in the pool. If you increase the number of control tasks in a suite, the number of suites available to the Toloker decreases by the same number.

There shouldn't be too few pages available. Otherwise:

- You won't be able to correctly evaluate the quality of the Toloker's responses.
- The Toloker won't be interested in completing such tasks because they'll spend a lot of time studying instructions but won't earn much.

{% cut "Example" %}

#### A large pool with 1% of control tasks (good)

There are 10,000 tasks in the pool, and 100 of them are control tasks (1%). Each suite contains 10 tasks, and 1 of them is a control task. Hence, a user can complete up to 100 suites.

#### A small pool with 1% control tasks (bad)

There are 100 tasks in the pool, and 1 of them is a control task (1%). Each suite contains 10 tasks, and 1 of them is a control task. Hence, each user can only complete 1 suite.

#### A small pool with 10% control tasks (good)

There are 100 tasks in the pool, and 10 of them are control tasks (10%). Each suite contains 10 tasks, and 1 of them is a control task. Hence, each user can complete up to 100 suites

{% endcut %}

{% endcut %}

If there are few control tasks in the open pool, [add new control tasks](../troubleshooting/pool-setup.md#add-gs).

{% cut "What for" %}

In a large pool with few control tasks, a situation might occur when users who have completed a lot of tasks in the project stop getting new task suites. This happens when the Toloker completes all control tasks in the pool.

{% endcut %}

{% note info %}

To filter out Tolokers, use the [Control tasks](control.md) quality control rule. To rank Tolokers by the quality of responses in control tasks, use a [skill](nav.md).

{% endnote %}

{% endcut %}

{% endcut %}

{% cut "How long does the markup performed by experts take?" %}

This process usually takes about 6 hours. The estimated time of the markup completion is indicated in the **Edit tasks** section.

{% endcut %}

{% cut "What should I do if the markup process failed?" %}

If the markup process failed for one reason or another, contact support. Go to the tab for control tasks or to the pool page and click {% if locale == "en-com" %}**Contact us**{% endif %}. After the problem is solved, you'll be able to order the markup of control tasks again.

{% endcut %}

{% include [contact-support](../_includes/contact-support-help.md) %}