# Sandbox

{% note tip %}

If you are looking for the answer to a specific question, use **Ctrl+F** to search the page (**Cmd+F** on MacOS).

{% endnote %}

{% cut "Why don't I see my task in the Sandbox?" %}

Make sure that:

1. The [pool](../../glossary.md#pool) is started.

1. The Toloker is added as a trusted user.

1. The trusted user is registered in the sandbox as a Toloker.

1. The trusted user didn't use social networks when registering.

1. Your trusted Toloker matches the [filters](../../glossary.md#filters) you set.

{% endcut %}

{% cut "What do I do if an error occurs on the server when I try to export a project from the Sandbox?" %}

#### Try exporting the project without pools.

Select an exported project and don't select pools in the window that opens.Click **Export**.

#### If the error persists, refresh the token.

Go to [ Yandex ID]({{ passport-profile }}).Under **Sign in and device history**, click **Log out from all devices**.Request new tokens in the Sandbox and main environment.Update the token in the [Sandbox]({{ sandbox-profile-integration }})**Profile **.

{% endcut %}

{% cut "Why isn't anything happening when a test Toloker clicks **Submit** in the sandbox?" %}

Use your requester account to preview the pool and check whether it's possible to submit a task. If this fails, most likely there is an error in your project.

{% endcut %}

{% cut "I can't add a trusted user." %}

Possible reasons:

- The Toloker isn't registered in the sandbox. The account you registered in the Toloka production version won't work. Make sure you have specified the correct _Toloker's_ account as a trusted one.

- The Toloker's account is authorized via social networks.[Register]({{ register }}) a new user in Yandex.

{% endcut %}

[Other questions](troubleshooting.md)

{% include [contact-support](../_includes/contact-support.md) %}