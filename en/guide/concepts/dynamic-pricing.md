# Setting up pricing

The price is indicated per [task suite](../../glossary.md#task-suite) in US dollars. For cents, use the dot (“.”) as a separator.

If the value of the **Pool type** in advanced settings is **General tasks**, the minimum price per task suite is $0.005. For other [pool](../../glossary.md#pool) types, you can set the price to zero.

In Toloka, there are two ways to set the task price:

- _Fixed pricing_: Sets the price per task suite. The price will be the same for any Toloker, regardless of their [skills](../../glossary.md#skill) and experience.

- _Dynamic pricing_: Allows you to additionally set other prices that depend on the Toloker's skill. For example, to pay more to those who have a higher skill.

    Create a skill, and then assign it to Tolokers automatically or manually. For more information, see [Skills](nav.md). [How do I set up dynamic pricing?](dynamic-pricing.md#section_ucl_3hl_vlb)

## How do I determine the optimal price? {#section_wb1_lhl_vlb}

Every Toloker wants to earn more, so it is difficult to give exact figures. To find out the price you need to set, follow the recommendations:

- Pay attention to the price suggest under the **Price per task suite, $** field. It contains the recommended price based on the minimum wage of the countries selected in the filters.

  {% note warning "Restriction" %}

  The price suggest is available to a limited number of requesters.

  {% endnote %}

- Pay attention to the **Toloker interest at this price** indicator. It shows how your price meets expectations of Tolokers. If the interest is low, you can raise price per task suite to have a bigger number of Tolokers in the project. If the interest is high, you can reduce price to save money.

- Turn on the stopwatch and measure how long it will take to read the [instructions](../../glossary.md#instructions) and complete several of your tasks. Calculate how many task suites you would complete in an hour and think what price would be fair.

- If your task is not urgent, set a minimum price and see how many Tolokers get interested. This way you can determine the optimal price based on the demand for your tasks.

- [Register]({{ register }}) as a Toloker (you will need an additional account on Yandex) and estimate the average earnings per hour for different tasks. Try to find tasks similar to yours.

{% note info %}

The high task price doesn't guarantee a good quality of the result. Increasing the price allows you to attract more Tolokers, but the quality of the result depends on the quality of the Tolokers themselves. Good Tolokers can be paid more using dynamic pricing.

{% endnote %}

### Price per item {#price-per-item}

When you're creating or editing a pool, under the **Price per task suite, $** field you can see price per 1 [item](../../glossary.md#item).

Price per item is calculated as:

#|
||
price per 1 item ![](../_images/other/icons/equal.svg) price per task suite ![](../_images/other/icons/multiply.svg) overlap ![](../_images/other/icons/divide.svg) tasks per suite ![](../_images/other/icons/plus.svg) fee
||
|#

### What is the suggested price based on? {#price-suggest}

The price suggested for the items in your pool depends on several factors:

- The type of the project and the preset you chose while [creating the project](project.md).

- The Tolokers who match the [filters](filters.md) you set for the pool.

- The minimal wage in the countries where the filtered Tolokers come from (some filters can affect it indirectly, like the Tolokers' language filter).

The combination of all the above factors affect the suggested price.

## Setting up dynamic pricing {#section_ucl_3hl_vlb}

To set up dynamic pricing:

1. For dynamic pricing, you need a skill. Learn how to create and assign skills in the [Skills](nav.md) section.

    To increase the Toloker's motivation, make the skill [public](nav.md#public). The Toloker will see the full list of prices and their level.

1. When creating or editing a [pool](../../glossary.md#pool), specify a fixed price in the **Price per task suite, $**. This price will be used if the skill is not assigned to the Toloker.

1. In the advanced settings, enable the **Use dynamic pricing** option.

1. Choose a skill in the window that opens.

1. The skill value is a number from 0 to 100. Set the price for each range of skill values.

{% note info %}

The price is calculated when the task suite is assigned to the Toloker. If the skill changed or was assigned after the Toloker submitted a completed assignment, only the next assignment will be at the new price.

{% endnote %}

#### Example of dynamic pricing settings

![](../_images/location-job/dynamic-pricing.png)

## What's next {#what_next}

- [Add tasks](pool.md) to the pool.
- Learn more about how to set up a pool:

    - [Dynamic overlap](dynamic-overlap.md).
    - Selective [majority vote](selective-mvote.md) control.
    - [Filters](filters.md).
    - [Speed/quality balance](adjust.md).
    - [Setting up quality control](qa-pool-settings.md).
    - [Reviewed assignments](offline-accept.md).

## See also {#see-also}

- [Crowdsourcing concepts: Pricing](https://toloka.ai/knowledgebase/pricing/)
- [{#T}](nav.md)

## Troubleshooting {#troubleshooting}

{% include [faq-set-task-price](../_includes/faq/finance/set-task-price.md) %}

{% include [faq-set-up-budget](../_includes/faq/finance/set-up-budget.md) %}

{% include [faq-pay-more-optional-fields](../_includes/faq/finance/pay-more-optional-fields.md) %}

{% include [faq-awards-statistics](../_includes/faq/finance/awards-statistics.md) %}

{% include [faq-tasks-with-different-prices](../_includes/faq/finance/tasks-with-different-prices.md) %}

[Get closing documents and invoices](../troubleshooting/support.md#feedback_g3b_vj3_qjb)

[Return the funds transferred to the Toloka account](../troubleshooting/support.md#feedback_khw_wc3_qjb)

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles-internal.md) %}