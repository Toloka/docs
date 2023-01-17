# Speed/quality balance

By default, your tasks are available to all Tolokers. If you set [filters](filters.md), they are available only to those who match them.

When there are many Tolokers, you can get results quickly, but the quality of the Tolokers' responses may be poor. The number of [active Tolokers](../../glossary.md#active-tolokers) (who will see the task if you publish it now) is displayed in the {% if locale == "en-com" %}**TOP %**{% endif %} tab to the left of the slider:

![](../_images/location-job/adjust_percentage.png)

You can select Tolokers for your task based on a personalized quality forecast.

## How does it work? {#how-it-works}

A personalized quality forecast is based on a large amount of data about user behavior in the system, how other users completed your task, and the task itself. Based on this data, we predict in real time how well each particular user will handle your task. We select the best Tolokers by comparing quality forecasts for all users.

## Improve the quality of results {#concept_cgm_vzq_xlb}

You can select only the best Tolokers using one of the filters in the [personalized quality forecast](../../glossary.md#personilized-quality-forecast):

- {% if locale == "en-com" %}**TOP %**{% endif %} — Allows you to set the percentage of the best Tolokers who will have access to your task.

- {% if locale == "en-com" %}**Online**{% endif %} — Allows you to set the maximum number of the best Tolokers who will have access to your task.

## Recommendations {#concept_gtb_2zk_xlb}

- Make sure that the total number of Tolokers exceeds the one required to complete your task several times. Otherwise, your task may not be completed due to lack of Tolokers.

- If you don't know what settings to choose, make the task available only to the best Tolokers. For example, set 20% in the {% if locale == "en-com" %}**TOP %**{% endif %} setting. If the tasks completion speed is insufficient, increase the value to get results faster.

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

{% include [troubleshooting-speed-dropped](../_includes/troubleshooting/pool-setup/speed-dropped.md) %}

{% include [faq-speed-up-completion](../_includes/faq/pool-setup/speed-up-completion.md) %}

{% include [contact-support](../_includes/contact-support.md) %}