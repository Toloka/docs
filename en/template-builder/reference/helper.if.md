# helper.if

The If...Then...Else operator. Allows you to execute either one block of code or another, depending on the condition. If you need more options, use [helper.switch](helper.switch.md).

For example, if you want to conduct a survey, you can use the `helper.if` component to ask the gender of the respondent and add different sets of questions, depending on whether the respondent is male or female.

**How it works:**
If the condition in `if` is true (returns `true`), the code specified in the `then` property will be executed. Otherwise (the condition is false and returns `false`) the code specified in `else` will be executed.

The `else` property is optional. For example, let's say you ask the user "did you Like the image". You can make a comment field appear when a negative response is received, but nothing happens when a positive response is received.

[View example in the sandbox](https://clck.ru/asSdk).

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "helper.if" | Set component type ||
|| `condition`<span style="color: red">\*</span> | _condition_ | Condition to check. ||
|| `else` | _any_ | The element that is returned if the condition from the `condition` property is false (returns `false`). ||
|| `then`<span style="color: red">\*</span> | _any_ | The element that is returned if the condition from the `condition` property is true (returns `true`). ||
|#
