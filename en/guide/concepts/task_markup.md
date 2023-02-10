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

- For other types of projects, you can request this feature by contacting [support](../troubleshooting/support.md).

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

1. Click **Edit** in the **Pool tasks** section.

1. Go to the **General** tab.

1. In the **We can label control tasks for you** section, click **Try it for free**.

1. Click **Order**. Your pool data will be sent for markup to expert Tolokers. For better quality, we use algorithms that select tasks that can be used as control tasks.

1. Wait until the markup is completed. This process usually takes about 6 hours. The estimated time of markup completion is indicated in the **Edit tasks** section.

1. After the markup is completed, the tasks are uploaded back to the pool. In the **Edit tasks** section on the **Control tasks** tab, you'll see the following message: “Control tasks are ready”. You can [edit](task-markup-by-yourself.md#task-edit) and [delete](task-markup-by-yourself.md#delete-task) the control tasks you received.

{% note info %}

If the markup process failed for some reason, contact support. Go to the tab for control tasks or to the pool page and click **Contact us**. After the problem is solved, you'll be able to request control task markup again.

{% endnote %}

## What's next {#what_next}

- [Add a training pool](train.md).
- [Top up your account](refill.md).
- [Start the pool](pool-run-and-stop.md).

## See also {#see-also}

- [{#T}](distribute-tasks-by-pages.md)
- [Efficiency indicators: Control tasks](./efficiency-metrics/control-tasks-share.md)
- [Efficiency indicators: Control task balance](./efficiency-metrics/control-tasks-balance.md)

## Troubleshooting {#troubleshooting}

{% include [faq-how-many-control-tasks](../_includes/faq/pool-setup/how-many-control-tasks.md) %}

{% include [faq-how-long-labeling-experts](../_includes/faq/result-questions/how-long-labeling-experts.md) %}

{% include [troubleshooting-labeling-failed](../_includes/troubleshooting/result-questions/labeling-failed.md) %}

{% include [contact-support](../_includes/contact-support.md) %}