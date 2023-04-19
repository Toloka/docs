# Property types

In the [component](../reference/index.md) descriptions, each property has a type. This page contains explanations for these types.

#### "component.name"

For the `type` property, the name of the component is indicated everywhere. If you specify a different name, that would be a different component.

#### action

Any [action component](../reference/actions.md). Components with the name `actions.*` let you perform various actions, such as show notifications.

#### any

Any value. Those might be:
- Standard JSON elements: string, number, `true`, `false`, object, or array.
- [Helpers](../reference/helpers.md) that return a value.
- Other components, if allowed in the configuration.
- References to other places in the configuration using the structure `{ "$ref": "path.to.element" }`. Use this type of linking for [code reuse](../best-practices/reuse.md).

#### array

Array of comma-separated elements. You can use as an array element:

- Standard JSON elements: string, number, `true`, `false`, object, or array.
- [Helpers](../reference/helpers.md) that return a value.
- Other components, if allowed in the configuration.
- References to other places in the configuration using the structure `{ "$ref": "path.to.element" }`. Use this type of linking for [code reuse](../best-practices/reuse.md).

An array is enclosed in square brackets, `[]`:

```json
"cities": ["London", "Tokyo", "New York"]
```

#### boolean

Boolean value without quotation marks: `true` or `false`.

#### condition

Any component of the [condition](../reference/conditions.md). Use components with the name `conditions.*` to match an expression against a condition. For example, you can check that a text field is filled in.

#### integer

An integer without quotation marks, for example, `25`.

#### number

A number without quotation marks. The separator of the fractional and integer parts is the dot. For example, `25.5`.

#### object

A list of `"key":value` pairs separated by commas. Enclosed in curly brackets `{}`.
```json
{
  "name": "John",
  "surname": "Smith"
}
```

#### ref

A pointer to a visual component using the construction `{ "$ref": "path.to.element" }`.

[View example](https://ya.cc/t/AiIEBqw-3YbMBH)

{% note info %}

The list of components you can link to might be limited. For example, [action.play-pause](../reference/action.play-pause.md) works only with the components that support audio or video playback.

{% endnote %}

#### string

A string enclosed in quotation marks. For example: `"Hello world"`.

#### writable

Component you can write the data to: `data.internal` or `data.output`. In some components, you can use `data.relative`. [Learn more about components](../operations/work-with-data.md).

#### visual

A visual component (`layout.*`, `view.*`, `field.*`) or [helper](../reference/helpers.md) that returns it. See the list in the [component reference guide](../reference/index.md).

{% include [contact-support](../_includes/contact-support.md) %}