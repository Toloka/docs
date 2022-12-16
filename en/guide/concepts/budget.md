# Managing the requester's personal account

To send tasks for completion, you must have money in your Toloka account. {% if locale == "en-com" %}For more information, see [Topping up your account](refill.md).{% endif %}

All payments between requesters and Tolokers are made in U.S. dollars. The account balance is shown in the main menu:

![](../_images/other/balance-ru.png)

- The green number is the account balance.

- Gray indicates funds reserved for the tasks waiting to be [reviewed](../../glossary.md#assignment-review).

Money in the account is spent on the following items:

- [Payment per task](#task-payment)

- [Fee](#comission)

- [Rewards for Tolokers](bonus.md)

You can [track spending](#track-budget) in your profile. You can also download a task report in a PDF file. To monitor the funds available in your account, [set up notifications](#money-notification).

## Payment per task {#task-payment}

The price of a task is set by the requester in the [pool settings](../../glossary.md#pool). Money is deducted from the account as tasks are completed. If you [review assignments](accept.md) after they are completed, the money for [completed tasks](../../glossary.md#completed-tasks) is first reserved, and then deducted.

## Fees {#comission}

The requester is charged a fee for using Toloka — a percentage of the cost of tasks including [rewards](bonus.md). It is 30%, but not less than $0.001.

The amount by project is shown in your [profile]({{ profile }}) (on the {% if locale == "en-com" %}**Spent**{% endif %} tab). You can see total fees for the pool tasks on the pool page (the {% if locale == "en-com" %}**Budget spent (+ markup)**{% endif %} and {% if locale == "en-com" %}**Approximate budget (+ markup)**{% endif %} fields).

## Expenses in the requester's profile {#track-budget}

To see your spending history:

1. Go to the [requester profile]({{ profile }}) and switch to the {% if locale == "en-com" %}**Spent**{% endif %} tab.

1. Under the **Spending history** title, select a period.

1. Select the type of the expenses:

    - {% if locale == "en-com" %}**All costs**{% endif %} —  all expenses for the period.

    - {% if locale == "en-com" %}**Reserved**{% endif %} — reserved money for the period.

1. In the section below you will see:

    - **Total spent** — the sum of all payments and fees for the selected period.

    - **Reserved money** — funds reserved for the tasks waiting to be reviewed.
    
    - Details by dates in the **Payment** and in the **Fees** columns.

{% note info %}

To save the report with the spending data in the PDF file format, click {% if locale == "en-com" %}**Download report as PDF**{% endif %}. To choose another file format, click ![](../_images/other/drop-down.svg) at the right.

{% endnote %}

## Get invoices and bills {#invoices}

1. Go to the [requester profile]({{ profile }}) and switch to the {% if locale == "en-com" %}**Spent**{% endif %} tab.

1. Click **Get invoices and bills**.

1. Select a period in the **Date**, **of invoice from**, **till** fields. Also you can use **extended search** to set additional search parameters.

1. Click **Show invoices** or **download the extended report as an MS Excel file**.

## Notifications of account status {#money-notification}

To get notifications when you have less than 5 dollars left on your account:

1. Go to the [requester profile]({{ profile }}) and switch to the {% if locale == "en-com" %}**Notifications**{% endif %} tab.

1. In the **Low funds** row, choose which notification method to use:

    - **Browser** — push notifications will appear at the bottom of the screen. To enable notifications in the browser, click **Turn on** in the **Browser** column.

    - **Messages** — notifications will be displayed on the [Messages]({{ messages }}) page.

    - **Email** — notifications will be sent to the email specified in your profile.

## Main and secondary accounts {#parent-child-accounts}

Requesters who opted for a paper contract can create main and secondary accounts.

#### Limitations:

- Only accounts without any projects can be main and secondary accounts.

- We recommend the post-paid type of contract for main and secondary accounts.

#### Keep in mind the following:

- General [skills](../../glossary.md#skill).

- Each secondary account has its own password and username.

- You can't convert a secondary account into the main one.

- Payments are only available for the main account, from which the funds are distributed to secondary accounts.

- Financial reports and closing documents are issued to the main account and are not sent to secondary accounts.

If you want to create main and secondary accounts, [write to support](../troubleshooting/support.md).

## Troubleshooting {#troubleshooting}

{% cut "When I top up my account, I see an amount 1000 times greater than I planned. What happened?" %}

That's normal. For example, if you entered $25 and you see "25,000", it's still $25 with a decimal delimiter. Your account will be topped up by $25 at the current exchange rate. You'll see the amount in rubles when you proceed to payment.

{% endcut %}

{% cut "Why do we pay 20% VAT in the invoice?" %}

In accordance with Clause 3.8. of our [Requester agreement]({{ customeragreement-probki }}), the VAT is charged in addition to the cost of services and included in the invoice. This is the same as paying VAT on purchases at any store. Your account in Toloka will be topped up by the amount you entered.

{% endcut %}

{% cut "How long does paying the invoice take?" %}

If you pay using a bank card, the money is usually transferred to your Toloka account within a few minutes. If you can't see the top-up amount on your account, [write to us](../troubleshooting/support.md) and we'll sort it out. Specify your requester username and account number and use **Account top-up** as your email subject.

{% endcut %}

{% cut "How do I find out the currency exchange rate that would apply to my account top-up in Toloka?" %}

You specify the top-up amount in USD. On the **Balance**, it's converted into rubles, including VAT. [Learn more](refill.md) about top-up.

{% endcut %}

{% cut "How do I add money to Toloka?" %}

You can top up your Toloka account using a bank card or bank transfer. On the [Profile]({{ profile }}) page, click "Connect to billing", fill out the form, and you'll see the "Top up account" button. [Learn more](refill.md#step-by-step) with step-by-step instructions.

[Get closing documents and invoices](../troubleshooting/support.md)

[Refund money transferred to the Toloka account](../troubleshooting/support.md)

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}
