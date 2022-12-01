# Questions about presets

{% note tip %}

If you are looking for the answer to a specific question, use **Ctrl+F** to search the page (**Cmd+F** on MacOS).

{% endnote %}

## Area selection {#concept_bdk_qgd_rmb}

{% cut "I have a task for area selection in an image. What should the Toloker do if there is no selectable object in the image?" %}

Main options:

- Select an arbitrary area in the image (for example, put a square in the upper-right corner). In this case, the project instructions for reviewers should also reflect this.

- Ask the Toloker to skip the task and report it in a personal message. Messages are reviewed by the requester. If the object is truly missing, the task is deleted from the pool by resetting the overlap.

- Add an additional “No object” checkbox to the interface. Make sure that your JS checks that either the object is selected or the checkbox is enabled. In this case, add information about the checkbox value in the review task interface.

{% endcut %}

{% include [contact-support](../_includes/contact-support-help.md) %}