1. Click **Add a pool** on the project page.

1. {% include [toloka-requester-pool-name](../../../_includes/toloka-requester-source/id-toloka-requester-source/pool-name.md) %}

1. {% include [toloka-requester-pool-description](../../../_includes/toloka-requester-source/id-toloka-requester-source/pool-description.md) %}

1. Click **Create**.

1. Follow the steps in the pool wizard:

    {% include [toloka-requester-pool-description](../../../_includes/toloka-requester-source/id-toloka-requester-source/pool-wizard-apply.md) %}

    1. **Select the audience for your task**

        Select Tolokers using [filters](../../../../glossary.md#filters). Tasks will only be shown to matching Tolokers, rather than to all of them.

        Click the **Add filter** button and set the filter parameters.

    1. **Setup quality control**

        {% include [toloka-requester-source-quality-control](../../../_includes/toloka-requester-source/id-toloka-requester-source/quality-control.md) %}

        To learn more, see the [Quality control overview](../../../../guide/concepts/quality-control-overview.md) section.

    1. **Set the task price and overlap**

        In the **Price per task suite, $** field, set the amount of money to pay per task suite done by one Toloker.

        {% include [toloka-requester-source-tolokers-interest](../../../_includes/toloka-requester-source/id-toloka-requester-source/tolokers-interest.md) %}

        In the **Overlap** field, define how many Tolokers must do each task.

        You can also set up [dynamic pricing](../../../../glossary.md#dynamic-pricing) and [dynamic overlap](../../../../glossary.md#dynamic-overlap).

    1. **Prepare and upload data**

        [Upload tasks](../../../../guide/concepts/task_upload.md) to the pool. This step will be enabled after you complete the previous steps.

    1. **Add control tasks for checking performance**

        Add [control tasks](../../../../glossary.md#control-task) to monitor the quality of task completion:

        1. Enter correct responses.

        2. Select the fields to use.

        3. Click **Save and go to next** or **Skip task**.

        4. Click **Save all control tasks**.

        {% include [toloka-requester-source-step-enabled](../../../_includes/toloka-requester-source/id-toloka-requester-source/step-enabled.md) %}

    1. **Double-check your project and try out tasks**

        At this step, check how the task will look from the Toloker's point of view.

        {% include [toloka-requester-source-step-enabled](../../../_includes/toloka-requester-source/id-toloka-requester-source/step-enabled.md) %}

    1. **Add optional pool settings**

        Set up advanced pool settings.

        {% note info %}

        This step will be enabled after you complete the previous steps. You can skip this step by clicking **Use default settings**.

        {% endnote %}

{% include [toloka-requester-source-pool-is-ready](../../../_includes/toloka-requester-source/id-toloka-requester-source/pool-is-ready.md) %}