# Archiving pools and projects

{% note info %}

If you are looking for the answer to a specific question, use **Ctrl+F** to search the page (**Cmd+F** on MacOS).

{% endnote %}


{% cut "Can I delete a pool?" %}

You can't completely delete a pool, but you can archive it. The system won't delete my pools automatically.

{% endcut %}

{% cut "How long is the pool stored?" %}

If there is no activity in the pool for a month, it is archived. You can't run such a pool, but you can clone it or download the labeled data from it.

{% endcut %}

{% cut "Where are my pools that were closed a few months ago stored?" %}

Inactive pools are archived after one month. To see them, select **Archived** in the **Pools** tab.

{% endcut %}

{% cut "How do I find out the pool archiving parameters?" %}

To find out the archiving date, get a [list of operations]({{ get-operations-list }}) with the `POOL.ARCHIVE` type. The response will contain the pool number and the archiving date. You can't get the method used to archive the pool via the API.

If less than a month passed between the activity in the pool and its archiving, you can assume that the pool was archived manually, and if it's been one month or more, then it was archived automatically.

{% endcut %}

{% cut "How do I accept tasks from the archived pool or when the Toloker wrote to me later than the allowed deadline?" %}

Simply [give the Toloker a separate reward](../concepts/bonus.md) without changing the task status. You can't change the task status in the pool in this case.

{% endcut %}

[Other questions](support.md#help)

{% include [contact-support](../_includes/contact-support-help.md) %}