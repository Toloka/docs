# Filter Tolokers with confirmed language knowledge

_Use pool filters to filter the Tolokers with various languages for which they passed the language test._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Specify pool filter {#step-three}

[Find out](get-pools.md) the ID of the pool where you want to add the language filter.

```python
from toloka.client.primitives.operators import InclusionOperator

updated_pool = toloka_client.[get_pool](*get_pool)('38955320')
updated_pool.filter=(
    (toloka.filter.[Languages](*Languages)(operator=[InclusionOperator](*InclusionOperator).IN, value=['EN', 'DE'], verified=True)) &
    (toloka.filter.[Languages](*Languages)(operator=[InclusionOperator](*InclusionOperator).IN, value=['FR'], verified=True))
)
toloka_client.[update_pool](*update_pool)(pool_id=updated_pool.id, pool=updated_pool)
```

{% note tip %}

See the [Filter Tolokers](filter-tolokers.md) Toloka-Kit recipe for examples of other filters you can use for pools.

{% endnote %}

{% cut "Languages filter in the Toloka interface" %}

The image below shows how the selected language filter looks in the pool interface.

![Filters used for pool](../_images/recipes/filter-languages.png =700x)

{% endcut %}

### 4. Print created pool filter {#step-four}

The `update_pool()` request will return the [Pool](../reference/toloka.client.pool.Pool.md) class object. You can use its attributes to print the information you need.

```python
print(updated_pool.filter)
```

You should get an output with the created pool filter which looks like this.

```bash
FilterAnd(_unexpected={}, and_=[FilterOr(_unexpected={}, or_=[FilterAnd(_unexpected={}, and_=[Languages(_unexpected={}, operator=<InclusionOperator.IN: 'IN'>, value='EN'), Skill(_unexpected={}, key='26366', operator=<CompareOperator.EQ: 'EQ'>, value=100)]), FilterAnd(_unexpected={}, and_=[Languages(_unexpected={}, operator=<InclusionOperator.IN: 'IN'>, value='DE'), Skill(_unexpected={}, key='26377', operator=<CompareOperator.EQ: 'EQ'>, value=100)])]), FilterOr(_unexpected={}, or_=[FilterAnd(_unexpected={}, and_=[Languages(_unexpected={}, operator=<InclusionOperator.IN: 'IN'>, value='FR'), Skill(_unexpected={}, key='26711', operator=<CompareOperator.EQ: 'EQ'>, value=100)])])])
```

{% cut "Response description" %}

Parameter | Description
--------- | -----------
`and_` | The logical `AND` operator that specifies that all the conditions connected with it must be met.<br/><br/>The first `and_` operator here defines the relations between the first and the second parts of the filter: the Tolokers must know both French and one of the languages in the first part of the filter (English or German) to access the tasks in the pool.
`or_` | The logical `OR` operator that specifies that at least one of the conditions connected with it must be met.<br/><br/>In the first part of the filter it defines that the Tolokers must know either English or German.
`Skill.key='26366'` | Knowledge of the English language confirmed with a test.<br/><br/>The skill with the **26366** ID corresponds to the **Knowledge of English** platform-wide skill.<br/><br/>Use the [Get skill by ID](https://toloka.ai/docs/api/api-reference/#get-/skills/-id-) API method to view this skill details.
`Skill.key='26377'` | Knowledge of the German language confirmed with a test.<br/><br/>The skill with the **26377** ID corresponds to the **Deutschkenntnisse** platform-wide skill.<br/><br/>Use the [Get skill by ID](https://toloka.ai/docs/api/api-reference/#get-/skills/-id-) API method to view this skill details.
`Skill.key='26711'` | Knowledge of the French language confirmed with a test.<br/><br/>The skill with the **26711** ID corresponds to the **Connaissance du français** platform-wide skill.<br/><br/>Use the [Get skill by ID](https://toloka.ai/docs/api/api-reference/#get-/skills/-id-) API method to view this skill details.
`Skill.operator=<CompareOperator.EQ: 'EQ'>, value=100` | Specifies that the skill value must be equal to **100** (or 100%).

{% endcut %}

## Complete code: Filter Tolokers with confirmed language knowledge {#complete-code}

```python
import toloka.client as toloka
from toloka.client.primitives.operators import InclusionOperator

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

updated_pool = toloka_client.get_pool('38955320')
updated_pool.filter=(
    (toloka.filter.Languages(operator=InclusionOperator.IN, value=['EN', 'DE'], verified=True)) &
    (toloka.filter.Languages(operator=InclusionOperator.IN, value=['FR'], verified=True))
)
toloka_client.update_pool(pool_id=updated_pool.id, pool=updated_pool)

print(updated_pool.filter)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[Pool](../reference/toloka.client.pool.Pool.md) class_
- _[Languages](../reference/toloka.client.filter.Languages.md) class_
- _[get_pool()](../reference/toloka.client.TolokaClient.get_pool.md) method_
- _[InclusionOperator](../reference/toloka.client.primitives.operators.InclusionOperator.md) class_
- _[update_pool()](../reference/toloka.client.TolokaClient.update_pool.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](learn-basics.md)
- [{#T}](use-cases.md)
- [{#T}](../../guide/concepts/filters.md)
- [{#T}](filter-tolokers.md)
- [Toloka API: Edit pool](https://toloka.ai/docs/api/api-reference/#put-/pools/-id-)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*Pool]: [Pool](../reference/toloka.client.pool.Pool.md) class
[*get_pool]: [get_pool()](../reference/toloka.client.TolokaClient.get_pool.md) method
[*Languages]: [Languages](../reference/toloka.client.filter.Languages.md) class
[*InclusionOperator]: [InclusionOperator](../reference/toloka.client.primitives.operators.InclusionOperator.md) class
[*update_pool]: [update_pool()](../reference/toloka.client.TolokaClient.update_pool.md) method

{% include [image-styles](../../../_includes/image-styles-internal.md) %}