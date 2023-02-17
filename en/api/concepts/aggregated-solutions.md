# Overview

Aggregate accepted responses for tasks with an [overlap](../../glossary.md#overlap) in a [pool](../../glossary.md#pool) of 2 or more to get the final response with the degree of confidence.

You can aggregate responses in two ways:

- Yes — Aggregate responses by skill (`WEIGHTED_DYNAMIC_OVERLAP`).
- No — Aggregate responses using the Dawid-Skene method (`DAWID_SKENE`).

    The Dawid-Skene aggregation model works with [control](../../glossary.md#control-task) and [training](../../glossary.md#training-task) tasks as well as with general tasks. Responses specified for control tasks might not match the actual responses to the task if Tolokers often submit an incorrect response to it.

    The Dawid-Skene aggregation model automatically evaluates `|L|²` parameters for each Toloker, where `L` is the number of different aggregation values. Note that these parameters are determined automatically and are only used in calculations.

    Because the Dawid-Skene method evaluates `|L|²` parameters for each Toloker, we don't  recommend using it when the Toloker labels `< |L|²` tasks. In this case, the quality of aggregation may be poor.

    Aggregation via the interface and via the API works differently. When using the Dawid-Skene aggregation model, you can't aggregate more than one field via the API. You can only do that via the interface.

## Methods {#methods}

Method | Endpoint | Overview
----- | ----- | -----
POST | [/aggregated-solutions/aggregate-by-pool](aggregate-by-pool.md) | Starts aggregating responses to all completed tasks in the pool.
POST | [/aggregated-solutions/aggregate-by-task](aggregate-by-task.md) | Starts aggregating responses to a single task.
GET | [/aggregated-solutions/<operation_id>](get-aggregated-result.md) | Gets aggregated responses.

## See also {#see-also}

- [{#T}](../../guide/concepts/result-aggregation.md)

{% include [contact-support](../../guide/_includes/contact-support.md) %}