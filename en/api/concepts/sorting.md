# Sorting the list of objects

When you request a list of objects using the `GET` method, you can specify the parameters to sort the list by. Sorting is set in the request using the **sort** query parameter.

{% note info %}

Lists of objects support various sorting options. For more information about the parameters, see the `GET` request description for each object.

{% endnote %}

{% cut "Toloka objects that can be sorted" %}

- [Projects](get-prj-list.md)
- [Pools](get-pool-list.md)
- [Trainings](get-training-list.md)
- [Subscriptions to events](get-webhook-subscriptions-list.md)
- [Skills](get-skill-list.md)
- [Toloker skills](get-user-skill-list.md)
- [Task access bans](ban-get-list.md)
- [Tasks](get-tasks-list.md)
- [Task suites](get-task-suite-list.md)
- [Operations](get-operations-list.md)
- [Responses](result.md)
- [Files in responses](get-attachment-list.md)
- [Aggregated responses](get-aggregated-result.md)
- [Bonuses](get-bonus-list.md)
- [Threads of messages to Tolokers](get-chain-list.md)

{% endcut %}

## Sorting direction {#direction}

You can sort values in ascending or descending order.

For example, when using `sort=id`, the list is sorted by identifier values in ascending order. To change the sorting direction to descending, add a hyphen before the parameter: `sort=-id`.

## Sorting by multiple parameters {#plurality}

When sorting, you can use one or multiple parameters at once. Simply specify them separated by a comma: `param1,param2`.

{% note info %}

The order of parameters affects the sorting sequence.

{% endnote %}

For example, when using `sort=param1,param2`, the list is sorted in ascending order by the `param1` values first, and then by the `param2` values. To change the sorting sequence, switch the parameters around: `sort=param2,param1`.

{% include [contact-support](../../guide/_includes/contact-support.md) %}