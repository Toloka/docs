# Sandbox

The [Sandbox]({{ sandbox }}) is a testing environment for Toloka. This is where you can test your [project](../../glossary.md#project-ru) settings as a Toloker before moving them to the [Toloka production version]({{ production-version }}) and running the project for real Tolokers. This helps you avoid making mistakes and spending money on a task that isn't working right.

{% note alert %}

Note that you can move only project and [pool](../../glossary.md#pool-ru) settings. You can't move tasks and responses to them. The project's [quality control](../../glossary.md#quality-control-ru) settings can't be moved, either.

{% endnote %}


## How to run a project in the sandbox {#section_zmz_t4z_mlb}

1. Register in the sandbox as a requester. To do this, follow the [link]({{ sandbox }}).

    {% note info %}

    To avoid confusion, use the same Yandex ID that you used in the Toloka production version to register as a requester.

    {% endnote %}

1. Configure and launch your project:
    - A list of instructions is provided in [Tutorials for popular tasks](usecases.md).
    - General instructions in the [Starting and tuning a project](main-steps.md) section.

## How to complete tasks {#self}

To complete your tasks in the sandbox:

1. Register in the sandbox as a Toloker (see the instructions in the [user documentation]({{ user-documentation }}) ).
    {% note warning %}

    Authorization via social media isn't allowed, so you need to [register]({{ register }}) a new user in Yandex.

    {% endnote %}

1. Log in to the sandbox using the requester account.

1. Open the [Tolokers]({{ users }}) page and click {% if locale == "en-com" %}**Add trusted Tolokers**{% endif %}.

1. Click {% if locale == "en-com" %}**Add Toloker**{% endif %} and enter the case-sensitive username of the created Toloker.

    Only trusted Tolokers can access your tasks.

    The number of trusted Tolokers required for testing depends on the [overlap settings](dynamic-overlap.md).

    To test your project in the Sandbox, set [overlap](../../glossary.md#overlap-ru) 1. If you increase the overlap, you will need to register more Tolokers and add trusted accounts.

    When exporting a project to the production version of [Toloka](#export), you can specify the necessary overlap in accordance with your project goals.

1. Log in to the sandbox using the Toloker account and test your tasks. Make sure that the buttons and response validation are set up correctly, and assess how long it takes to complete the tasks. Make sure that the [Toloker selection](filters.md) and [quality control](control.md) work.

## How to move a task to the production version of Toloka {#export}

To move tasks from the sandbox to the production version:

1. Link the sandbox and production version's accounts:

    1. Open the {% if locale == "en-com" %}**External Services Integration**{% endif %} tab in the production version on the [profile]({{ profile }}) page and copy the OAuth token.

    1. Open the same tab in the sandbox on the [profile]({{ sandbox-profile }}) page and paste the copied token into the **Production OAuth token** field.

1. Go to the project page in the sandbox and click .

1. Choose the pools to export and click **Export**.

    If to the pool has [linked training](train.md), it is exported automatically.


## Troubleshooting {#troubleshooting}

#### How do I work with the Sandbox?

[Register]({{ sandbox }}) as a requester in the sandbox.

[Register]({{ sandbox-for-performers }}) as a Toloker using another account.

In your requester account, add your Toloker account to your trusted list.

Create and run a task. It will appear in the list of tasks for your trusted users. For more information, see [Help](sandbox.md).

#### How do I see my pool through the eyes of a Toloker?

To test your task, add yourself as a trusted Toloker in the Sandbox. To do this, on the **Tolokers** page, click **Add trusted users**. Enter the username for the Toloker's account (case-sensitive).

#### Is it possible to use the same account for the Sandbox and the public Toloka version?

No, you need a separate account for each version of Toloka. To create a task in the [Sandbox](../../glossary.md#sandbox-ru), [register](access.md) in it as a requester. To complete your own task, register another account for yourself as a Toloker.

#### What do I do if an error occurs on the server when I try to export a project from the Sandbox?

#### Try exporting the project without pools.
Select an exported project and don't select pools in the window that opens.Click **Export**.
#### If the error persists, refresh the token.
Go to [ Yandex ID]({{ passport-profile }}).Under **Sign in and device history**, click **Log out from all devices**.Request new tokens in the Sandbox and main environment.Update the token in the [Sandbox]({{ sandbox-profile-integration }})**Profile **.

#### How do I check my project in the mobile version of Toloka?

To do this, you will need a Sandbox version of the Toloka app. [Write to support](../troubleshooting/support.md#support-work-toloka) to get it.

#### Will a copy of the project exported from the Sandbox be updated in the main version if I edit the original?

You won't be able to update a previously exported project. If you clone a project from the sandbox again, its current copy is added. The old project doesn't change.

#### Why isn't anything happening when a test Toloker clicks **Submit** in the sandbox?

Use your requester account to preview the pool and check whether it's possible to submit a task. If this fails, most likely there is an error in your project.

#### How do I move control tasks from the Sandbox to the main pool?

The tasks themselves are not exported, only the project configuration and the settings of the selected pool. You can download the completed tasks from the pool in the Sandbox and import them to the exported pool.

To download only the control tasks (if you completed them in the interface), go to **Mark up**, then click **Control tasks** and **Download**.

#### Why don't I see my task in the Sandbox?

Make sure that:

1. The [pool](../../glossary.md#pool-ru) is started.
1. The Toloker is added as a trusted.
1. The trusted user is registered in the sandbox as a Toloker.
1. The trusted user didn't use social networks when registering.
1. Your trusted user matches the [filters](../../glossary.md#filtering-ru) you set.

#### I can't add a trusted user.

Possible reasons:

- The Toloker isn't registered in the sandbox. The account you registered in the Toloka production version won't work. Make sure you have specified the correct _Toloker's_ account as a trusted one.
- The Toloker's account is authorized via social networks.[Register]({{ register }}) a new user in Yandex.

#### What overlap should I set?

Overlap defines how many Tolokers complete the same pool task.

The best overlap is an overlap that provides satisfying quality of results. For most tasks that are not [reviewed](../../glossary.md#left-off-acceptance-ru), overlap from "3" to "5" is enough. If the tasks are simple, overlap of "3" is likely to be enough. For tasks that are reviewed, set overlap to "1".

#### Can I change overlap after the pool is started?

Yes. [Open edit mode for the pool](pool-edit.md) and set a new overlap value. You don't need to restart the pool. Updating the settings is usually fast, but if there are many tasks, it may take several minutes.

{% include [contact-support](../_includes/contact-support-sandbox.md) %}