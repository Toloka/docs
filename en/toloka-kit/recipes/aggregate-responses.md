# Aggregate responses in pool

_Aggregate the responses from Tolokers for all completed tasks in a pool._

{% note tip %}

We recommend that you try our [crowd-kit library](../../crowd-kit/index.md). It has various aggregation methods and executes on your computer.

{% endnote %}

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Configure aggregation operation {#step-three}

Set up the parameters which you want to use for the aggregation: in this example we choose tasks from the pool with the `pool_id` value, set the aggregation type to `DAWID_SKENE`, and specify output fields to aggregate. The `aggregate_solutions_by_pool()` method starts the aggregation.

```python
aggregation_operation = toloka_client.[aggregate_solutions_by_pool](*aggregate_solutions_by_pool)(
    type=toloka.aggregation.AggregatedSolutionType.DAWID_SKENE,
    pool_id='36502086',
    fields=[toloka.aggregation.PoolAggregatedSolutionRequest.Field(name='result')]
)
```

### 4. Start aggregation and wait for result {#step-four}

Aggregation takes some time depending on the number of tasks and responses from Tolokers. The `wait_operation()` method displays the progress of the aggregation operation and shows when it finishes.

```python
aggregation_operation = toloka_client.[wait_operation](*wait_operation)(aggregation_operation)
```

The output from the code portion above will look like this.

```bash
100%|████████████████████████████████████████████| 100/100 [00:52<00:00,  1.92it/s]
```

### 5. Display aggregation results {#step-five}

After the aggregation operation 100% finished, get the results with the help of the `get_aggregated_solutions()` method and iterate through them.

```python
aggregation_results = toloka_client.[get_aggregated_solutions](*get_aggregated_solutions)(aggregation_operation.id)
for result in aggregation_results:
    print(result.task_id, result.output_values['result'])
```

You should get an output with the task IDs and the `result` output data values which looks like this.

```bash
00022cfa46--637cf3e76e13181a0164e4b3 cat
00022cfa46--637cf3e76e13181a0164e4b7 cat
00022cfa46--637cf3e76e13181a0164e4bc dog
00022cfa46--637cf3e86e13181a0164e4c0 cat
00022cfa46--637cf3e86e13181a0164e4c4 cat
00022cfa46--637cf3e86e13181a0164e4c8 dog
00022cfa46--637cf3e86e13181a0164e4cd dog
00022cfa46--637cf3e86e13181a0164e4d0 dog
```

## Complete code: Aggregate responses in pool {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealApiKey_Here', 'PRODUCTION')

aggregation_operation = toloka_client.aggregate_solutions_by_pool(
    type=toloka.aggregation.AggregatedSolutionType.DAWID_SKENE,
    pool_id='36502086',
    fields=[toloka.aggregation.PoolAggregatedSolutionRequest.Field(name='result')]
)

aggregation_operation = toloka_client.wait_operation(aggregation_operation)

aggregation_results = toloka_client.get_aggregated_solutions(aggregation_operation.id)
for result in aggregation_results:
    print(result.task_id, result.output_values['result'])
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[aggregate_solutions_by_pool()](../reference/toloka.client.TolokaClient.aggregate_solutions_by_pool.md) method_
- _[wait_operation()](../reference/toloka.client.TolokaClient.wait_operation.md) method_
- _[get_aggregated_solutions()](../reference/toloka.client.TolokaClient.get_aggregated_solutions.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](learn-basics.md)
- [{#T}](use-cases.md)
- [Crowd-Kit](../../crowd-kit/index.md)
- [Toloka API: Aggregate responses in pool](https://toloka.ai/docs/api/api-reference/#post-/aggregated-solutions/aggregate-by-pool)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*aggregate_solutions_by_pool]: [aggregate_solutions_by_pool()](../reference/toloka.client.TolokaClient.aggregate_solutions_by_pool.md) method
[*wait_operation]: [wait_operation()](../reference/toloka.client.TolokaClient.wait_operation.md) method
[*get_aggregated_solutions]: [get_aggregated_solutions()](../reference/toloka.client.TolokaClient.get_aggregated_solutions.md) method