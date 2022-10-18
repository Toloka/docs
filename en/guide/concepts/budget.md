# Managing the requester's personal account

To send tasks for completion, you must have money in your Toloka account. {% if locale == "en-com" %}For more information, see [Topping up your account](refill.md).{% endif %}

All payments between requesters and Tolokers are made in U.S. dollars. The account balance is shown in the main menu:
![](../_images/other/balance-ru.png)
- The green number is the account balance.

- Gray indicates funds reserved for the tasks waiting to be [reviewed](../../glossary.md#left-off-acceptance).


Money in the account is spent on the following items:

- [Payment per task](#task-payment)

- [Fee](#comission)

- [Rewards for Tolokers](bonus.md)


You can [track spending](#track-budget) in your profile. You can also download a task report in a PDF file. To monitor the funds available in your account, [set up notifications](#money-notification).


## Payment per task {#task-payment}

The price of a task is set by the requester in the [pool settings](../../glossary.md#pool). Money is deducted from the account as tasks are completed. If you [review assignments](accept.md) after they are completed, the money for [completed tasks](../../glossary.md#submitted-answers) is first reserved, and then deducted.


## Fees {#comission}

The requester is charged a fee for using Toloka — a percentage of the cost of tasks including [rewards](bonus.md). It is 30%, but not less than $0.005.

The amount by project is shown in your [profile]({{ profile }}) (on the {% if locale == "en-com" %}**Expenses**{% endif %} tab). You can see total fees for the pool tasks on the pool page (the {% if locale == "en-com" %}**Budget spent (+ markup)**{% endif %} and {% if locale == "en-com" %}**Approximate budget (+ markup)**{% endif %} fields).


## Expenses in the requester's profile {#track-budget}

To see spending data in your profile, go to the {% if locale == "en-com" %}**Expenses**{% endif %} tab. Amounts are grouped by date, project, and pool:

- {% if locale == "en-com" %}**Sum**{% endif %}: Black indicates the amount spent, and gray indicates funds reserved for tasks waiting for review.

- {% if locale == "en-com" %}**Markup**{% endif %}: Fee for using Toloka.


You can set up email notifications and get messages when you have less than 5 dollars left on your account.


## Report on tasks {#stat-report}

To get the {% if locale == "en-com" %}Statistics on requester's tasks{% endif %} report with spending data:

1. Choose the period in the [requester profile]({{ profile }}) (on the {% if locale == "en-com" %}**Expenses**{% endif %} tab).

1. Click {% if locale == "en-com" %}**Generate report (pdf)**{% endif %} and download the PDF file.

    The report contains data on spending per project (including markup) and [rewards](../../glossary.md#bonus) paid (the {% if locale == "en-com" %}**Reward**{% endif %} row).



## Notifications of account status {#money-notification}

To get notifications when your account has less than 5 dollars remaining, click {% if locale == "en-com" %}**Edit**{% endif %} in the [requester profile]({{ profile }}). Select options:

- {% if locale == "en-com" %}**Enable notifications**{% endif %}.

- {% if locale == "en-com" %}**Send copies of notifications by email**{% endif %}, if you want to get messages by email.



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

If you want to create main and secondary accounts, [write to support](../troubleshooting/support.md#new).


## Troubleshooting {#troubleshooting}

{% cut "How do I connect to billing from Moscow or Saint Petersburg?" %}

If the address is in Saint Petersburg, enter Saint Petersburg in the **Region** field, then specify the street, house number, and postal code. You don't need to fill out the other fields.

If the address is in Moscow, enter Moscow in the **Region** field, then specify the street, house number, and postal code. [Learn more](refill.md#step-by-step) about connecting to billing.

If it still doesn't work, [enter](../troubleshooting/troubleshooting.md) your full address with the postal code in the feedback form. We'll help you fill out the fields correctly.

{% endcut %}

{% cut "When I top up my account, I see an amount 1000 times greater than I planned. What happened?" %}

That's normal. For example, if you entered $25 and you see "25,000", it's still $25 with a decimal delimiter. Your account will be topped up by $25 at the current exchange rate. You'll see the amount in rubles when you proceed to payment.

{% endcut %}

{% cut "Why do we top up our account in a non-Russian currency?" %}

Toloka is an international platform for users from different countries. The platform is provided by the Swiss company Yandex Services AG.

{% endcut %}

{% cut "Why do we pay 20% VAT in the invoice?" %}

In accordance with the tax legislation of the Russian Federation, we have included Clause 3.8. in our [Requester agreement]({{ customeragreement-probki }}): the VAT is charged in addition to the cost of services and included in the invoice. This is the same as paying VAT on purchases at any store. Your account in Toloka will be topped up by the amount you entered.

{% endcut %}

{% cut "How long does paying the invoice take?" %}

If you pay using a bank card, the money is usually transferred to your Toloka account within a few minutes. If you can't see the top-up amount on your account, [write to us](../troubleshooting/support.md#help) and we'll sort it out. Specify your requester username and account number and use **Account top-up** as your email subject.

{% endcut %}

{% cut "How do I find out the currency exchange rate that would apply to my account top-up in Toloka?" %}

You specify the top-up amount in USD. On the **Balance**, it's converted into rubles, including VAT. The conversion follows the Central Bank of Russia's exchange rate at the time of invoicing (UTC). [Learn more](refill.md) about top-up.

{% endcut %}

{% cut "How do I add money to Toloka?" %}

You can top up your Toloka account using a bank card or bank transfer. On the [Profile]({{ profile }}) page, click "Connect to billing", fill out the form, and you'll see the "Top up account" button. [Learn more](refill.md#step-by-step) with step-by-step instructions.

{% endcut %}

[Get closing documents and invoices](../troubleshooting/support.md#feedback_g3b_vj3_qjb)

[Refund money transferred to the Toloka account](../troubleshooting/support.md#feedback_khw_wc3_qjb)

{% include [contact-support](../_includes/contact-support-help.md) %}
