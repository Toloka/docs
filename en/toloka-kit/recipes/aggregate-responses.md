# Aggregate responses

{% list tabs %}

- Aggregate responses in pool

  ```python
  import toloka.client as toloka

  toloka_client = toloka.TolokaClient('AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE', 'PRODUCTION')

  aggregation_operation = toloka_client.aggregate_solutions_by_pool(
      type='WEIGHTED_DYNAMIC_OVERLAP',
      pool_id='1238218',
      answer_weight_skill_id='91dbfd8f1bc3310fbbbd09f64b8ab6e5',
      fields=[toloka.aggregation.PoolAggregatedSolutionRequest.Field(name='result')]
  )
  print(aggregation.output_values['result'])
  ```

- Aggregate responses to single task

  ```python
  import toloka.client as toloka

  toloka_client = toloka.TolokaClient('AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE', 'PRODUCTION')

  aggregation = toloka_client.aggregate_solutions_by_task(
      pool_id='1238218',
      task_id='000012e4ca--62e97a75dbab805456309d81',
      answer_weight_skill_id='91dbfd8f1bc3310fbbbd09f64b8ab6e5',
      fields=[toloka.aggregation.PoolAggregatedSolutionRequest.Field(name='result')]
  )
  print(aggregation.output_values['result'])
  ```

{% endlist %}