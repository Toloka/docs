# Setting up a pool

{% note tip %}

If you are looking for the answer to a specific question, use **Ctrl+F** to search the page (**Cmd+F** on MacOS).

{% endnote %}

## Filters {#filters}

{% cut "The Tolokers completed training for the first pool and got the skill. A week later, we cloned the pool, but all the Tolokers lost their skill. Do all the Tolokers need to complete the training again?" %}

The validity period of the training skills is controlled by the **Retry after** parameter. The skill is deleted after a period specified in days in the **Retry after** field, if the Toloker:

- Has a skill value lower than the one specified in the **Level required** field.

- Didn't complete any tasks linked to training during this period.

Your Tolokers will need to be trained again.

{% endcut %}

{% cut "Why is my project not available in the mobile version of Toloka?" %}

Tasks in pools are automatically available in the web version of Toloka and the mobile app. Check the pool settings. You might have the `Client = Toloka web version`[filter](../concepts/filters.md) on.

{% endcut %}

[Other questions](support.md#help)

## Quality control {#quality-control}

{% cut "I set up quality control, then I copied my user requirements. All my quality control settings were deleted and replaced with the copied settings. Is that normal?" %}

Yes. When you copy the filter and quality control settings, the settings you previously added manually are overwritten. You should see a warning about this in the copy settings window.

{% endcut %}

{% cut "When I export a project from the Sandbox, the task files are not exported. Is this how it's supposed to work? I suddenly lost the markup of the control tasks that I created in the sandbox." %}

The tasks themselves are not exported, only the project configuration and the settings of the selected pool. However, you can download your marked up tasks from the **Sandbox** pool and import them to the pool you created. To download the control tasks only (if you marked them up in the interface), go to **Mark up**, then click **Control tasks** and **Download**.

{% endcut %}

{% cut "I want to create an exam with three tasks. If a user does two out of three tasks correctly, they get the skill. So I try to use `3` in the **Recent control task responses to use** field, but I get an error that the value is too small. Can I get around this without increasing the number of tasks to five?" %}

The **Recent control task responses to use** field is for the number of recent responses from the Toloker. If you use non-automatic acceptance for your task, then to set up your intended rule you need to specify `3` in **Total reviewed responses**.

{% endcut %}

{% cut "Why has the speed of pool completion dropped?" %}

Possible reasons:

- You've stopped the [main pool](../../glossary.md#training-pool). This could limit the number of Tolokers with access to the pool. Start the training pool again. There will be more Tolokers who can access the tasks.

- The filters you set are too strict. For example, a strong restriction on a certain skill that most users don't have.

- Too many users are banned. Ease the quality control rules.

{% endcut %}

[Other questions](support.md#help)

## Overlap {#overlap}

{% cut "Why is the maximum number of submitted assignments in the progress bar less than the total number of uploaded tasks?" %}

The progress bar shows the number of task suites including the overlap. If the overlap is greater than one, the number of task suites is different from the total number of tasks.

{% endcut %}

[Other questions](support.md#help)

{% include [contact-support](../_includes/contact-support-project-setting.md) %}