# Overview

A pool consists of task suites that are sent out for completion at the same time. In the pool properties, you set the task price, overlap, [Toloker selection filters](filters.md), [quality control rules](quality_control.md), and so on.

If the project has multiple pools, the order for completing them depends on the parameters:

- Pools with identical filter settings and price per task are assigned to Tolokers in the order in which they were started. The pool that was started earlier will be completed sooner. You can [change the order for completing the pools](create-pool.md#priority).

- Pools with different filter settings and/or a different price per task are sent out for completion when the [pool opens](open-pool.md).

## Methods {#methods}

Method | Endpoint | Overview
----- | ----- | -----
POST | [/pools](create-pool.md) | Creates a pool.
POST | [/pools/<pool_id>/close-for-update](close-pool-for-update.md) | Closes a pool for editing.
PUT | [/pools/<pool_id>](edit-pool.md) | Makes changes to a pool.
POST | [/pools/<pool_id>/open](open-pool.md) | Opens a pool.
POST | [/pools/<pool_id>/close](close-pool.md) | Closes a pool.
POST | [/pools/<pool_id>/archive](archive-pool.md) | Moves a pool to the archive.
POST | [/pools/<pool_id>/clone](clone-pool.md) | Creates a duplicate pool.
GET | [/pools](get-pool-list.md) | Gets a list of created pools (including archived pools).
GET | [/pools/<pool_id>](get-pool.md) | Gets the properties of a pool.
PATCH | [/pools/pool_id>](set-priority-pool.md) | Changes the priority of a pool.

## Learn more {#links}

- [Description of the pool in the Requester's guide](../../guide/concepts/pool-main.md)