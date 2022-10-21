# Sandbox

{% note tip %}

If you are looking for the answer to a specific question, use **Ctrl+F** to search the page (**Cmd+F** on MacOS).

{% endnote %}

{% cut "How do I work with the Sandbox?" %}

[Register]({{ sandbox }}) as a requester in the sandbox.

[Register]({{ sandbox-for-performers }}) as a Toloker using another account.

In your requester account, add your Toloker account to your trusted list.

Create and run a task. It will appear in the list of tasks for your trusted users. For more information, see [Help](../concepts/sandbox.md).

{% endcut %}

{% cut "Why don't I see my task in the Sandbox?" %}

Make sure that:

1. The [pool](../../glossary.md#pool) is started.

1. The Toloker is added as a trusted user.

1. The trusted user is registered in the sandbox as a Toloker.

1. The trusted user didn't use social networks when registering.

1. Your trusted Toloker matches the [filters](../../glossary.md#filtering) you set.

{% endcut %}

{% cut "How do I see my pool through the eyes of a Toloker?" %}

To test your task, add yourself as a trusted Toloker in the Sandbox. To do this, on the **Tolokers** page, click **Add trusted users**. Enter the username for the Toloker's account (case-sensitive).

{% endcut %}

{% cut "What do I do if an error occurs on the server when I try to export a project from the Sandbox?" %}

#### Try exporting the project without pools.

Select an exported project and don't select pools in the window that opens.Click **Export**.

#### If the error persists, refresh the token.

Go to [ Yandex ID]({{ passport-profile }}).Under **Sign in and device history**, click **Log out from all devices**.Request new tokens in the Sandbox and main environment.Update the token in the [Sandbox]({{ sandbox-profile-integration }})**Profile **.

{% endcut %}

{% cut "How do I check my project in the mobile version of Toloka?" %}

To do this, you will need a Sandbox version of the Toloka app. [Write to support](support.md#support-work-toloka) to get it.

{% endcut %}

{% cut "Will a copy of the project exported from the Sandbox be updated in the main version if I edit the original?" %}

You won't be able to update a previously exported project. If you clone a project from the sandbox again, its current copy is added. The old project doesn't change.

{% endcut %}

{% cut "Why isn't anything happening when a test Toloker clicks **Submit** in the sandbox?" %}

Use your requester account to preview the pool and check whether it's possible to submit a task. If this fails, most likely there is an error in your project.

{% endcut %}

{% cut "How do I move control tasks from the Sandbox to the main pool?" %}

The tasks themselves are not exported, only the project configuration and the settings of the selected pool. You can download the completed tasks from the pool in the Sandbox and import them to the exported pool.

To download only the control tasks (if you completed them in the interface), go to **Mark up**, then click **Control tasks** and **Download**.

{% endcut %}

{% cut "Is it possible to use the same account for the Sandbox and the public Toloka version?" %}

No, you need a separate account for each version of Toloka. To create a task in the [Sandbox](../../glossary.md#sandbox), [register](../concepts/access.md) in it as a requester. To complete your own task, register another account for yourself as a Toloker.

{% endcut %}

{% cut "I can't add a trusted user." %}

Possible reasons:

- The Toloker isn't registered in the sandbox. The account you registered in the Toloka production version won't work. Make sure you have specified the correct _Toloker's_ account as a trusted one.

- The Toloker's account is authorized via social networks.[Register]({{ register }}) a new user in Yandex.

{% endcut %}

[Other questions](support.md#feedback_oyr_m5s_hlb)

{% include [contact-support](../_includes/contact-support-help.md) %}