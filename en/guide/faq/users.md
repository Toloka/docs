# Tolokers

{% note tip %}

If you are looking for the answer to a specific question, use **Ctrl+F** to search the page (**Cmd+F** on MacOS).

{% endnote %}

## Data about Tolokers {#user-info}

{% cut "How do I view information about Tolokers?" %}

You can view information about Tolokers of your tasks on the [Tolokers]({{ users }}) page. To view information about a Toloker, select their ID. The requester can access the following data in the Toloker profile: country and city, age, education, language skills. On the **Metainformation** tab, you can find the versions of the browser and operating system, the User-agent type, region detected by IP, and other Toloker parameters. To select the Tolokers for your [pool](../../glossary.md#pool) based on their profile, device, geo location, and other parameters, use [filters](../concepts/filters.md).

{% endcut %}

{% cut "Do you verify the information entered by the Toloker in the profile?" %}

It's the Toloker's responsibility to provide the information in the profile during registration. We don't request identity documents for registering in Toloka. If a profile seems suspicious to us, we ask the owner to confirm the information.

{% endcut %}

{% cut "Do Tolokers know their ID?" %}

No, only the requester can see the Toloker ID.

{% endcut %}

{% cut "Why can I filter Tolokers by gender in the pool settings, if gender isn't shown in the profile?" %}

The requester can't see the full details about specific Tolokers. For example, the requester can't see their date of birth, gender, last name, or first name. However, filters by date of birth and gender are available to the requester in the pool settings. You can use them to select a group of Tolokers without accessing the details about specific Tolokers. This decreases the risk of Toloker de-anonymization.

{% endcut %}

## Rewards {#bonuses}

{% cut "How do I reward Tolokers in addition to the basic task price?" %}

You can increase the basic task price for Tolokers that have a higher skill. To do this, set up [Dynamic pricing](../concepts/dynamic-pricing.md). If you want to motivate high-quality Tolokers regardless of their skill, use [rewards](users.md). In your task instructions, specify the amount and conditions for the Toloker rewards.

{% endcut %}

{% cut "How can I view statistics on paid rewards?" %}

To view your expenses that involve rewards, go to your [profile]({{ profile }}) and open the **Expenses** tab.

{% endcut %}

## Cheaters {#cheaters}

{% include [faq-disable-tasks](../_includes/faq/result-questions/disable-tasks.md) %}

{% cut "Can I ask a Toloker to redo the task if they made mistakes in it?" %}

No. After sending a task, the Toloker can't make any changes to it. You can add tasks that were [completed](../../glossary.md#completed-tasks) incorrectly to a new pool.

{% endcut %}

{% include [faq-fix-myself](../_includes/faq/result-questions/fix-myself.md) %}

{% cut "Fraudulent Tolokers submit assignments with empty response fields. Are they going to be banned before the responses of other Tolokers are known?" %}

Fraudulent Tolokers aren't banned before the [majority vote](../concepts/mvote.md) is known. That's why we recommend that you have new Tolokers complete [training](../concepts/train.md) or a test. Then you can select the Tolokers that successfully completed the training to do your tasks.

{% endcut %}

{% cut "Are the cheaters who were banned for incorrect responses paid anyway?" %}

If the Toloker was already paid for the tasks, you can't cancel the payment.

{% endcut %}

{% cut "How can I ban a user and reject all their responses?" %}

You can't automatically reject the responses of a banned Toloker.

But you can do it yourself if you want. When downloading the results, select the option **Exclude assignments by banned users** to delete the responses of Tolokers who were banned at the moment of downloading. You can also forward all the assignments from banned users to other Tolokers using the [Re-completion of assignments from banned users](../concepts/restore-task-overlap.md) rule.

{% endcut %}

{% cut "Contact support" %}

<iframe width="100%" frameborder="0" src="https://forms.yandex.com/surveys/10035353.388b5c1d02f16762f4a79b515beaa9740148362a/?lang=en&iframe=1&service=toloka-ai"></iframe>

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}