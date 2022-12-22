# Type
`toloka.client.pool.dynamic_overlap_config.DynamicOverlapConfig.Type` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/pool/dynamic_overlap_config.py#L25)

The algorithm for dynamic overlap.

## Attributes Description

| Name | Value | Description |
| :------| :-----------| :----------| 
`BASIC`|'BASIC'|<p>Each response is assigned a weight depending on the Toloker&#x27;s skill value. The aggregated response confidence is calculated based on the probability algorithm. The task overlap increases until it reaches max_overlap or until the confidence of the aggregated response exceeds min_confidence. You have to specify max_overlap, min_confidence, answer_weight_skill_id and fields.</p>
