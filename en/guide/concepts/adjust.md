# Speed/quality balance

By default, your tasks are available to all Tolokers. If you set [filters](filters.md), they are available only to those who match them.

When there are many Tolokers, you can get results quickly, but the quality of the Tolokers' responses may be poor.

If you want to improve speed or quality of labeling, use the **Speed/quality balance** pool setting.

It allows you to select Tolokers based on a [personalized quality forecast](../../glossary.md#personilized-quality-forecast):

- **TOP %** — allows you to set the percentage of top-rated Tolokers who will have access to your task.

  {% cut "Example" %}

  ![](../_images/location-job/adjust_percentage_top.png)

  Only 40% of top-rated Tolokers will have access to your task.

  {% endcut %}

- **Online** — allows you to set the maximum number of top-rated Tolokers who will have access to your task.

  {% cut "Example" %}

  ![](../_images/location-job/adjust_percentage_online.png)

  Only 3000 of top-rated Tolokers will have access to your task.

  {% endcut %}

## How does it work? {#how-it-works}

A personalized quality forecast is based on a large amount of data about user behavior in the system, how other Tolokers completed your task, and the task itself. Based on this data, we predict in real time how well each particular user will handle your task. We select top-rated Tolokers by comparing quality forecasts for all Tolokers.

## Recommendations {#concept_gtb_2zk_xlb}

- Make sure that the total number of Tolokers exceeds the one required to complete your task several times. Otherwise, your task may not be completed due to lack of Tolokers.

- If you don't know what settings to choose, make the task available only to top-rated Tolokers. For example, set 20% in the **TOP %** setting. If the tasks completion speed is insufficient, increase the value to get results faster.

## What's next {#what-next}

- [Add tasks](pool.md) to the pool.
- Learn more about how to set up a pool:

    - [Setting up pricing](dynamic-pricing.md).
    - [Dynamic overlap](dynamic-overlap.md).
    - Selective [majority vote](selective-mvote.md) control.
    - [Filters](filters.md).
    - [Setting up quality control](qa-pool-settings.md).
    - [Reviewed assignments](offline-accept.md).

## See also {#see-also}

- [{#T}](nav.md)

## For developers {#for-developers}

- [Toloka-Kit: TopPercentageByQuality class](../../toloka-kit/reference/toloka.client.pool.speed_quality_balance_config.TopPercentageByQuality.md)
- [Toloka-Kit: BestConcurrentUsersByQuality class](../../toloka-kit/reference/toloka.client.pool.speed_quality_balance_config.BestConcurrentUsersByQuality.md)

## Troubleshooting {#troubleshooting}

{% cut "Why has the speed of pool completion dropped?" %}

Possible reasons:

- You've stopped the [training pool](../../glossary.md#training-pool). This could limit the number of Tolokers with access to the pool. Start the training pool again. There will be more Tolokers who can access the tasks.

- The filters you set are too strict. For example, a strong restriction on a certain skill that most Tolokers don't have.

- Too many Tolokers are banned. Ease the quality control rules.

{% endcut %}

{% cut "How can I speed up the pool completion?" %}

- To motivate Tolokers, assign a [public skill](nav-create.md#public) and use [dynamic pricing](dynamic-pricing.md).

- Try to [increase the project rating](project_rating_stat.md), so that your task is higher in the list of tasks for Tolokers.

- Adjust the [quality-speed ratio](adjust.md).

- Set a higher [priority](pool_poolparams.md#priority) for the pool among other project pools.

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}