# Ban Tolokers

_Restrict the access to the tasks for Tolokers._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Restrict access to Toloker {#step-three}

#### Restrict access to specific pool

[Find out](get-pools.md) the ID of the pool to which you want to restrict access for a Toloker. Use the `set_user_restriction()` method with the pool ID as an argument to the `PoolUserRestriction` collector class to restrict access to it to the Toloker with the ID specified in the request.

```python
pool_restriction = toloka_client.[set_user_restriction](*set_user_restriction)(
    toloka.user_restriction.[PoolUserRestriction](*PoolUserRestriction)(
        user_id='1a5d5299e5a1d0a47605f51191e09ffc',
        private_comment='Banning Toloker access to pool',
        pool_id='38955320'
    )
)
```

#### Restrict access to specific project

[Find out](get-projects.md) the ID of the project to which you want to restrict access for a Toloker. Use the `set_user_restriction()` method with the project ID as an argument to the `ProjectUserRestriction` collector class to restrict access to it to the Toloker with the ID specified in the request.

```python
project_restriction = toloka_client.[set_user_restriction](*set_user_restriction)(
    toloka.user_restriction.[ProjectUserRestriction](*ProjectUserRestriction)(
        user_id='1f66ac40c616b717bbffce2a70dfe1f2',
        private_comment='Banning Toloker access to project',
        project_id='120798'
    )
)
```

#### Restrict access to all projects

Use the `set_user_restriction()` method with the `AllProjectsUserRestriction` collector class to restrict access to all your projects to the Toloker with the ID specified in the request.

```python
all_projects_restriction = toloka_client.[set_user_restriction](*set_user_restriction)(
    toloka.user_restriction.[AllProjectsUserRestriction](*AllProjectsUserRestriction)(
        user_id='240d5b7897f98c119cd892e34295587e',
        private_comment='Banning Toloker access to all projects'
    )
)
```

{% note info %}

You can specify the `will_expire` argument for all the collector classes above (`PoolUserRestriction`, `ProjectUserRestriction`, or `AllProjectsUserRestriction`). It defines the date when the ban will be removed from the Toloker. If you don't set it, the ban will be permanent.

{% endnote %}

### 4. Print created ban information {#step-four}

The `set_user_restriction()` request will return the [UserRestriction](../reference/toloka.client.user_restriction.UserRestriction.md) class object. You can use its attributes to print the information you need.

```python
print(pool_restriction.id, pool_restriction.created)
print(project_restriction.id, project_restriction.created)
print(all_projects_restriction.id, all_projects_restriction.created)
```

You should get an output with the IDs of the bans and the ban creation date and time which looks like this.

```bash
163294517 2023-07-18 15:31:27.945000+00:00
163294518 2023-07-18 15:31:28.459000+00:00
163294519 2023-07-18 15:31:29.992000+00:00
```

## Complete code: Ban Tolokers {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

pool_restriction = toloka_client.set_user_restriction(
    toloka.user_restriction.PoolUserRestriction(
        user_id='1a5d5299e5a1d0a47605f51191e09ffc',
        private_comment='Banning Toloker access to pool',
        pool_id='38955320'
    )
)
project_restriction = toloka_client.set_user_restriction(
    toloka.user_restriction.ProjectUserRestriction(
        user_id='1f66ac40c616b717bbffce2a70dfe1f2',
        private_comment='Banning Toloker access to project',
        project_id='120798'
    )
)
all_projects_restriction = toloka_client.set_user_restriction(
    toloka.user_restriction.AllProjectsUserRestriction(
        user_id='240d5b7897f98c119cd892e34295587e',
        private_comment='Banning Toloker access to all projects'
    )
)
print(pool_restriction.id, pool_restriction.created)
print(project_restriction.id, project_restriction.created)
print(all_projects_restriction.id, all_projects_restriction.created)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[set_user_restriction()](../reference/toloka.client.TolokaClient.set_user_restriction.md) method_
- _[PoolUserRestriction](../reference/toloka.client.user_restriction.PoolUserRestriction.md) class_
- _[ProjectUserRestriction](../reference/toloka.client.user_restriction.ProjectUserRestriction.md) class_
- _[AllProjectsUserRestriction](../reference/toloka.client.user_restriction.AllProjectsUserRestriction.md) class_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](learn-basics.md)
- [{#T}](use-cases.md)
- [{#T}](../../guide/concepts/ban.md)
- [{#T}](get-pools.md)
- [{#T}](get-projects.md)
- [Toloka-Kit: UserRestriction class](../reference/toloka.client.user_restriction.UserRestriction.md)
- [Toloka API: Block access to tasks](https://toloka.ai/docs/api/api-reference/#put-/user-restrictions)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*set_user_restriction]: [set_user_restriction()](../reference/toloka.client.TolokaClient.set_user_restriction.md) method
[*PoolUserRestriction]: [PoolUserRestriction](../reference/toloka.client.user_restriction.PoolUserRestriction.md) class
[*ProjectUserRestriction]: [ProjectUserRestriction](../reference/toloka.client.user_restriction.ProjectUserRestriction.md) class
[*AllProjectsUserRestriction]: [AllProjectsUserRestriction](../reference/toloka.client.user_restriction.AllProjectsUserRestriction.md) class