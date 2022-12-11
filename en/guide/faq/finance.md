# Payments

{% note tip %}

If you are looking for the answer to a specific question, use **Ctrl+F** to search the page (**Cmd+F** on MacOS).

{% endnote %}

## Adding funds to your account {#concept-1}

{% cut "Why do we pay 20% VAT in the invoice?" %}

In accordance with the tax legislation of the Russian Federation, we have included Clause 3.8. in our [Requester agreement]({{ customeragreement-probki }}): the VAT is charged in addition to the cost of services and included in the invoice. This is the same as paying VAT on purchases at any store. Your account in Toloka will be topped up by the amount you entered.

{% endcut %}

{% cut "How long does paying the invoice take?" %}

If you pay using a bank card, the money is usually transferred to your Toloka account within a few minutes. If you can't see the top-up amount on your account, [write to us](support.md#help) and we'll sort it out. Specify your requester username and account number and use **Account top-up** as your email subject.

{% endcut %}

{% cut "How do I find out the currency exchange rate that would apply to my account top-up in Toloka?" %}

You specify the top-up amount in USD. On the **Balance**, it's converted into rubles, including VAT. The conversion follows the Central Bank of Russia's exchange rate at the time of invoicing (UTC). [Learn more](../concepts/refill.md) about top-up.

{% endcut %}

{% cut "How do I add money to Toloka?" %}

You can top up your Toloka account using a bank card or bank transfer. On the [Profile]({{ profile }}) page, click "Connect to billing", fill out the form, and you'll see the "Top up account" button. [Learn more](../concepts/refill.md#step-by-step) with step-by-step instructions.

{% endcut %}

[Get closing documents and invoices](support.md#feedback_g3b_vj3_qjb)

## Payment for tasks {#concept-2}

{% cut "Where can I set or change the task price?" %}

The task price is set up in the pool. Open the pool editing page and find the **Price** section.

The price is set up for a task suite. If the suite contains 10 tasks, the price in that section is set for labeling the entire suite.

Please note that the minimum price per task suite is $0.005. Therefore, if you want to change the task price, you need to change the number of tasks per suite.

[Learn more about the task price](dynamic-pricing.md).

If you need help setting up pricing for your project, [contact](../troubleshooting/support.md) us.

{% endcut %}

{% cut "How do I set up a budget for my first task in Toloka?" %}

Here's the general rule of pricing: the more time is needed to complete the task, the higher the price is.

If the task is simple, like if the Toloker spends a few seconds to assess product relevance, then set the price to $0.01–$0.02 for 10 tasks (products) on the page.

If you register in Toloka as a Toloker, you can compare offers from other requesters.

Define the page price, multiply it by the overlap (it's usually 3–5 for a classification task) and add 20% VAT. Try topping up your account by $10 first, then continue topping it up based on the performance dynamics.

{% endcut %}

{% cut "How do I pay more to users who fill out optional fields?" %}

You can issue rewards after completion and describe the criteria for increased rewards in your task instructions. You can't change the task suite price dynamically based on the completion results.

{% endcut %}

{% cut "How can i view my expenses?" %}

1. Open the project page.

1. Go to the **Statistics** tab.

1. Go to **Budget**, find the **Average task price** and **Earnings per hour** charts.

    This data will help you understand the current cost of your tasks.

Similar statistics are available for each pool if you need more detail.

Learn more about [project](project-statistic.md) and [pool](pool_statistic-pool.md) statistics.

{% endcut %}

{% cut "Where do I find the statistics on the awards I paid?" %}

Track your money debited for rewards in {% if locale == "en-com" %}**Profile** → **Spent**{% endif %} tab.

{% endcut %}

{% cut "Can there be tasks with different prices in the pool?" %}

No. The price per task suite is the same for all tasks in the pool. You can create multiple pools with different prices or [change the price](../concepts/dynamic-pricing.md) depending on the Toloker skill using **Dynamic pricing**. You can [pay rewards](../concepts/bonus.md) to good Tolokers.

{% endcut %}

[Other questions](support.md#new)

## Refund {#concept-3}

[Refund money transferred to the Toloka account](support.md#feedback_khw_wc3_qjb)

{% include [contact-support](../_includes/contact-support-help.md) %}