{% cut "How do I set quality control in a pool correctly?" %}

The settings for [quality control](../../../../glossary.md#quality-control) rules depend on the type of tasks. General recommendations:

- Always use one or more ways to control quality of answers.

- Counting [fast responses](../../../../guide/concepts/quick-answers.md) makes sense for most tasks.

- If the Toloker has to choose between options (for example, by selecting checkboxes), check the answers using [majority vote](../../../../guide/concepts/mvote.md) or [control tasks](../../../../guide/concepts/goldenset.md).

- If the Toloker has to provide a task response as a text or link or upload a photo, the best way to control quality is by [reviewing assignments](../../../../guide/concepts/accept.md). You can outsource task acceptance to Tolokers. Create a task with a question (for example, “Is this phrase translated correctly?”) and possible responses (for example, “yes”/“no”). Set up [overlap](../../../../guide/concepts/dynamic-overlap.md) and [majority vote](../../../../guide/concepts/mvote.md) check.

- If a task is more like an opinion poll (for example, choosing nice pictures from a set), [majority vote](../../../../glossary.md#majority-vote) is not a good way to control quality. Make [control tasks](../../../../glossary.md#control-task) with artificial examples where the choice is evident.

{% endcut %}