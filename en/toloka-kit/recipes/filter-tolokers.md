# Filter Tolokers

_Use pool filters to specify the Toloker groups you want to pick your tasks._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Specify pool parameters {#step-three}

First, specify the parameters you want your pool to have. You can choose your own values or have your own set of the pool parameters. Refer to the [Pool](../reference/toloka.client.pool.Pool.md) class page for more details.

```python
new_pool = toloka.pool.Pool(
    # The ID of the project in which the pool is created
    project_id='133047',
    # The pool name you will see in the list and use to distinguish the pool from other ones
    private_name='Pool with filters',
    # The date when the pool is going to expire and will be closed
    will_expire=datetime(2030, 1, 1),
    # The reward for the task suite specified in U.S. dollars
    reward_per_assignment=0.05,
    # The maximum duration of the task suite completion available to Tolokers
    assignment_max_duration_seconds=60*5,
    # The filters used to select Tolokers
    filter=(
        (toloka.filter.[AdultAllowed](*AdultAllowed)==True) &
        (toloka.filter.[Citizenship](*Citizenship)=='US') &
        (toloka.filter.[ClientType](*ClientType)=='TOLOKA_APP') &
        (toloka.filter.[DeviceCategory](*DeviceCategory)=='SMARTPHONE') &
        (toloka.filter.[Education](*Education)=='MIDDLE') &
        (toloka.filter.[Gender](*Gender)=='MALE') &
        (toloka.filter.[Languages](*Languages).in_(['EN','DE','FR'])) &
        (toloka.filter.[OSFamily](*OSFamily)=='IOS') &
        (toloka.filter.[Skill](*Skill)('12648')>70)
    )
)
```

#### Filters used for pool

For this recipe, we use the following filters:

- **Adult content** ([AdultAllowed](../reference/toloka.client.filter.AdultAllowed.md) filter class): The pool tasks with the adult content will only be shown to Tolokers who have agreed to see them.
- **Citizenship** ([Citizenship](../reference/toloka.client.filter.Citizenship.md) filter class): The tasks will be shown only to the Tolokers from the countries specified in the filter.
- **Client** ([ClientType](../reference/toloka.client.filter.ClientType.md) filter class): The pool tasks will be available in the selected Toloka client, in our case, in the mobile app.
- **Device type** ([DeviceCategory](../reference/toloka.client.filter.DeviceCategory.md) filter class): The pool tasks will be available to the Tolokers with the specified devices.
- **Education** ([Education](../reference/toloka.client.filter.Education.md) filter class): The pool tasks will be available to the Tolokers with the specified education level.
- **Gender** ([Gender](../reference/toloka.client.filter.Gender.md) filter class): The pool tasks will be available to the Tolokers with the specified gender.
- **Languages** ([Languages](../reference/toloka.client.filter.Languages.md) filter class): The pool tasks will be available to the Tolokers with the specified languages. Read the [Filter Tolokers with confirmed language knowledge](filter-tolokers-languages.md) recipe to learn how to filter Tolokers with various languages for which they passed the language test.
- **Operating system** ([OSFamily](../reference/toloka.client.filter.OSFamily.md) filter class): The pool tasks will be available to the Tolokers who use devices with the specified operating systems.
- **Skill** ([Skill](../reference/toloka.client.filter.Skill.md) filter class): The pool tasks will be available to the Tolokers with the specified skill having the selected value.

{% note tip %}

See the [Filters](../reference/toloka.client.filter.AdultAllowed.md) section of the Toloka-Kit reference for the complete list of the available filters and their possible values.

{% endnote %}

{% cut "Selected filters in the Toloka interface" %}

The image below shows how the selected filters look in the pool interface.

![Filters used for pool](../_images/recipes/filters.png =700x)

{% endcut %}

### 4. Create pool on platform {#step-four}

This actually creates a pool in Toloka.

```python
new_pool = toloka_client.create_pool(new_pool)
```

### 5. Print created pool ID {#step-five}

The `create_pool()` request will return the [Pool](../reference/toloka.client.pool.Pool.md) class object. You can use its attributes to print the information you need.

```python
print(new_pool.id)
```

You should get an output with the created pool ID which looks like this.

```bash
1443815
```

## Complete code: Filter Tolokers {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

new_pool = toloka.pool.Pool(
    project_id='133047',
    private_name='Pool with filters',
    will_expire=datetime(2030, 1, 1),
    reward_per_assignment=0.05,
    assignment_max_duration_seconds=60*5,
    filter=(
        (toloka.filter.AdultAllowed==True) &
        (toloka.filter.Citizenship=='US') &
        (toloka.filter.ClientType=='TOLOKA_APP') &
        (toloka.filter.DeviceCategory=='SMARTPHONE') &
        (toloka.filter.Education=='MIDDLE') &
        (toloka.filter.Gender=='MALE') &
        (toloka.filter.Languages.in_(['EN','DE','FR'])) &
        (toloka.filter.OSFamily=='IOS') &
        (toloka.filter.Skill('12648')>70)
    )
)
new_pool = toloka_client.create_pool(new_pool)
print(new_pool.id)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[Pool](../reference/toloka.client.pool.Pool.md) class_
- _[AdultAllowed](../reference/toloka.client.filter.AdultAllowed.md) class_
- _[Citizenship](../reference/toloka.client.filter.Citizenship.md) class_
- _[ClientType](../reference/toloka.client.filter.ClientType.md) class_
- _[DeviceCategory](../reference/toloka.client.filter.DeviceCategory.md) class_
- _[Education](../reference/toloka.client.filter.Education.md) class_
- _[Gender](../reference/toloka.client.filter.Gender.md) class_
- _[Languages](../reference/toloka.client.filter.Languages.md) class_
- _[OSFamily](../reference/toloka.client.filter.OSFamily.md) class_
- _[Skill](../reference/toloka.client.filter.Skill.md) class_
- _[create_pool()](../reference/toloka.client.TolokaClient.create_pool.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](learn-basics.md)
- [{#T}](use-cases.md)
- [{#T}](../../guide/concepts/filters.md)
- [{#T}](filter-tolokers-languages.md)
- [Toloka API: Create pool](https://toloka.ai/docs/api/api-reference/#post-/pools)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*Pool]: [Pool](../reference/toloka.client.pool.Pool.md) class
[*create_pool]: [create_pool()](../reference/toloka.client.TolokaClient.create_pool.md) method
[*AdultAllowed]: [AdultAllowed](../reference/toloka.client.filter.AdultAllowed.md) class
[*Citizenship]: [Citizenship](../reference/toloka.client.filter.Citizenship.md) class
[*ClientType]: [ClientType](../reference/toloka.client.filter.ClientType.md) class
[*DeviceCategory]: [DeviceCategory](../reference/toloka.client.filter.DeviceCategory.md) class
[*Education]: [Education](../reference/toloka.client.filter.Education.md) class
[*Gender]: [Gender](../reference/toloka.client.filter.Gender.md) class
[*Languages]: [Languages](../reference/toloka.client.filter.Languages.md) class
[*OSFamily]: [OSFamily](../reference/toloka.client.filter.OSFamily.md) class
[*Skill]: [Skill](../reference/toloka.client.filter.Skill.md) class

{% include [image-styles](../../../_includes/image-styles-internal.md) %}