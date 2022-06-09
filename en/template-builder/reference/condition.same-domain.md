# condition.same-domain

Checks if the link that you entered belongs to a specific site. If it does, returns `true`, otherwise, `false`.

Links must be specified in full, including the protocol (http, https, ftp).

The `www.` subdomain is ignored when checking, meaning that links to `www.example.ru` and `example.ru` are considered to be the same.

[View example in the sandbox](https://clck.ru/apq6v).

How to pass a link address:

- Specify it explicitly as a string.
- [Get the value from your data](../operations/work-with-data. dita).
- Refer to another element using `$ref`.
- Use [helpers](helpers.md) and [conditions](conditions.md) to get the value.

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "condition.same-domain" | Set component type ||
|| `data` | _any_ | The link address to be checked. If you don't specify it, the value returned by the parent component (the one that contains `condition.same-domain`) is used. ||
|| `hint` | _string_ | Validation error message that the annotator will see ||
|| `original`<span style="color: red">\*</span> | _any_ | The link address that your link is compared to. ||
|#
