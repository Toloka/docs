# Overview

[A training pool](../../glossary.md#training-tasks) includes unpaid task suites. The training pool must be linked to the main pool.

After completing the training pool, the Toloker is assigned a skill equal to the percentage of correct responses. If the percentage is higher than or equal to the **Level required** value in the linked pool, the Toloker gets access to the main pool.

## Methods {#methods}

Method | Endpoint | Overview
----- | ----- | -----
POST | [/trainings](create-training.md) | Creates a training pool (training).
PUT | [/trainings/<training_pool_id>](edit-training.md) | Makes changes to a training pool.
POST | [/trainings/<training_pool_id>/open](open-training.md) | Opens a training pool.
POST | [/trainings/<training_pool_id>/close](close-training.md) | Closes a training pool.
POST | [/training/<training_pool_id>/archive](archive-training.md) | Moves a training pool to the archive.
POST | [/training/<training_pool_id>/clone](clone-training.md) | Creates a duplicate training pool.
GET | [/trainings](get-training-list.md) | Gets the list of created training pools (including archived pools).
GET | [/trainings/<training_pool_id>](get-training.md) | Gets the properties of a training pool.

## Learn more {#links}

- [More details about training pools](https://toloka.ai/docs/guide/concepts/train.html)