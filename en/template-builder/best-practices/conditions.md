# Reviewing assignments automatically

Define clear conditions for your task to ensure that you get the desired output. The conditions check that the performer did the required actions.

In [Toloka]({{ toloka-requester-index-dita }}), you can use conditions to automate the assignment review process. For example, the performer can't submit an assignment before they meet your required conditions.

## Review features {#features}

- What can be reviewed:
    - Output data in [fields.*](../reference/fields.md);
    - Input data in [views.*](../reference/views.md) and [layouts.*](../reference/layouts.md).

- Where to specify conditions:
    - In the `validation` property of the parent component.
    - In the `condition` property of [plugin.trigger](../reference/plugin.trigger.md).

- A link to the reviewed data is specified in the `data` property.
- Some components don't have the `data` property, and you can only access them from the `validation` property of the parent component (for example, [condition.played](../reference/condition.played.md) and [condition.played-fully](../reference/condition.played-fully.md)).

## Making a field mandatory {#condition-required}

To check that the data is filled in, add the [condition.required](../reference/condition.required.md) component.

In this example, the user must fill in the text field, otherwise the <q>Submit</q> button won't work. The [condition.empty](../reference/condition.empty.md) component works the opposite way: it checks if the data is empty and returns `false` if the data has a value.

[View example in the sandbox](https://clck.ru/QR9Qq).

## Comparing values {#condition-equals-or-not}

#### Checking that values are equal

To check that the preset value and output value are equal, use the component [condition.equals](../reference/condition.equals.md).

In this example, if the user responds <q>No</q>, a text entry field appears.

.

#### Checking that values are not equal

To return the values that don't meet the specified conditions, list them in the `condition` property of the [condition.not](../reference/condition.not.md) component.

In this example, if the `condition.equals` condition is met and returns `true`, `condition.not` returns `false` and hides the text entry field.

.

#### When there are multiple correct responses

To check that an array in `data` is a subarray for `parent`, add the component [condition.sub-array](../reference/condition.sub-array.md).

In this example, the component checks that the values `animal` and `human` are part of the `objects` array. If the responses <q>Human</q> and <q>Animal</q> are selected, the `helper.if` logical component displays the question: <q>Do the human and animal interact?</q>.

.

## Checking multiple conditions {#multiple-conditions}

#### Meeting all conditions

To check that multiple conditions are met, list them in the `condition` property of the [condition.all](../reference/condition.all.md) component.

In this example, the uses has to do two actions: fill out the text field and click the link in the interface. The <q>Submit</q> button won't work until both conditions are met.

.

#### Meeting at least one of the conditions

To check that at least one of the conditions is met, list the conditions in the `condition` property of the [condition.any](../reference/condition.any.md) component.

In this example, the user has to perform at least one of the two actions: select <q>Nothing is written there</q> or fill out the <q>What is written on the image?</q> field. The <q>Submit</q> button won't work until one of the conditions is met.

.

## Checking conditions for specific components {#component}

Some conditions work only with certain [components](../glossary.md#component-ru). For example, [condition.link-opened](../reference/condition.link-opened.md) works only with `view.link`.

In this example, the user has to click the link in the interface, otherwise the <q>Submit</q> button won't work.

.

## Can't find the desired component? {#schema}

In the [list of conditions](../reference/conditions.md), you can see all the available components with the name `conditions.*`. If you can't find the desired component in the list or want to use a preset [configuration](../glossary.md#konfig-ru), define a review in the [JSON Schema]({{ json-schema }}) format using [condition.schema](../reference/condition.schema.md).


[![](../_images/buttons/contact-support.svg)](../concepts/support.md)
