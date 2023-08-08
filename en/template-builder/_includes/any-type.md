Any value. Those might be:

- Standard JSON elements: string, number, `true`, `false`, object, or array.
- [Helpers](../reference/helpers.md) that return a value.
- Other components, if allowed in the configuration.
- References to other places in the configuration using the structure `{ "$ref": "path.to.element" }`. Use this type of linking for [code reuse](../best-practices/reuse.md).