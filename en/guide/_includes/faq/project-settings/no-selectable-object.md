{% cut "What should the Toloker do if there is no selectable object in the image in an area selection task?" %}

There are four options:

- [Decompose the task](../../../../guide/concepts/solution-architecture.md): First select images with the items you need, then select areas in them.

- Select an arbitrary area in the image. For example, put a square in the upper-right corner.

    Mention this in your instructions for reviewers.

- Ask the Toloker to skip the task and report it in a personal message. Messages are reviewed by the requester. If the selectable object is missing, the task is deleted from the pool (by resetting the overlap).

- Add the “No object” checkbox to the interface and make sure that your JS checks that either the object is selected or the checkbox is selected.

    For control purposes, add information about the value of this checkbox to the task interface.

{% endcut %}