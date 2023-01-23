# Sandbox

The [Sandbox]({{ sandbox }}) is a testing environment for Toloka. This is where you can test your [project](../../glossary.md#project) settings as a Toloker before moving them to the [Toloka production version]({{ production-version }}) and running the project for real Tolokers. This helps you avoid making mistakes and spending money on a task that isn't working right.

{% note alert "Restriction" %}

Note that you can move only project and [pool](../../glossary.md#pool) settings. You can't move tasks and responses to them. The project's [quality control](../../glossary.md#quality-control) settings can't be moved, either.

{% endnote %}

## How to run a project in the sandbox {#section_zmz_t4z_mlb}

1. Register in the sandbox as a requester. To do this, follow the [link]({{ sandbox }}).

    {% note tip %}

    To avoid confusion, use the same Yandex ID that you used in the Toloka production version to register as a requester.

    {% endnote %}

1. Configure and launch your project:

    - A list of instructions is provided in [Tutorials for popular tasks](usecases.md).

    - General instructions in the [Starting and tuning a project](main-steps.md) section.

## How to complete tasks {#self}

To complete your tasks in the sandbox:

1. Register in the sandbox as a Toloker (see the instructions in the [user documentation]({{ user-documentation }}) ).

    {% note alert %}

    Authorization via social media isn't allowed, so you need to [register]({{ register }}) a new user in Yandex.

    {% endnote %}

1. Log in to the sandbox using the requester account.

1. Open the [Tolokers]({{ users }}) page and click {% if locale == "en-com" %}**Add trusted Tolokers**{% endif %}.

1. Click {% if locale == "en-com" %}**Add Toloker**{% endif %} and enter the case-sensitive username of the created Toloker.

    Only trusted Tolokers can access your tasks.

    The number of trusted Tolokers required for testing depends on the [overlap settings](dynamic-overlap.md).

    To test your project in the Sandbox, set [overlap](../../glossary.md#overlap) 1. If you increase the overlap, you will need to register more Tolokers and add trusted accounts.

    When exporting a project to the production version of [Toloka](#export), you can specify the necessary overlap in accordance with your project goals.

1. Log in to the sandbox using the Toloker account and test your tasks. Make sure that the buttons and response validation are set up correctly, and assess how long it takes to complete the tasks. Make sure that the [Toloker selection](filters.md) and [quality control](control.md) work.

## How to move a task to the production version of Toloka {#export}

To move tasks from the sandbox to the production version:

1. Link the sandbox and production version accounts:

    1. Open the {% if locale == "en-com" %}**Integrations**{% endif %} tab in the production version on the [profile]({{ profile }}) page, click **Get OAuth token**, and copy the OAuth token displayed.

    1. Open the same tab in the sandbox on the [profile]({{ sandbox-profile }}) page, paste the copied token into the **Main Toloka OAuth token** field, and click **Add OAuth token**.

1. Go to the project page in the sandbox and click {% if locale == "en-com" %}**![Drop-down button](../_images/drop-down.svg) → ![Export button](../_images/location-job/project/export.svg) Export**{% endif %}.

1. Choose the pools to export and click **Export**.

    If the pool has [linked training](train.md), it is exported automatically.

## Troubleshooting {#troubleshooting}

{% include [faq-work-with-sandbox](../_includes/faq/sandbox/work-with-sandbox.md) %}

{% include [faq-see-pool-as-toloker](../_includes/faq/sandbox/see-pool-as-toloker.md) %}

{% include [faq-same-account](../_includes/faq/sandbox/same-account.md) %}

{% include [troubleshooting-export-error](../_includes/troubleshooting/sandbox/export-error.md) %}

{% include [faq-check-mobile-version](../_includes/faq/sandbox/check-mobile-version.md) %}

{% include [faq-copy-from-sandbox](../_includes/faq/sandbox/copy-from-sandbox.md) %}

{% include [troubleshooting-submit](../_includes/troubleshooting/sandbox/submit.md) %}

{% include [faq-move-control-tasks](../_includes/faq/sandbox/move-control-tasks.md) %}

{% include [troubleshooting-dont-see-task](../_includes/troubleshooting/sandbox/dont-see-task.md) %}

{% include [troubleshooting-cant-add-trusted-user](../_includes/troubleshooting/sandbox/cant-add-trusted-user.md) %}

{% include [faq-overlap](../_includes/faq/pool-setup/overlap.md) %}

{% include [faq-change-overlap](../_includes/faq/pool-setup/change-overlap.md) %}

{% include [contact-support](../_includes/contact-support.md) %}