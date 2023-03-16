# Clearing the entered values

Sometimes, you need to clear a value that a Toloker entered by mistake. You might need it when you have multiple "branches" of questions, each having multiple response options. The Toloker might first give answers triggering one branch, and then change their mind and give another answer.

To clear the entered values, use the [action.set](../reference/action.set.md) action and the `{ "$empty": true }` structure. You can call this action using a [button](../reference/view.action-button.md) or [trigger](../reference/plugin.trigger.md).

## Example {#section_t1s_fgt_xmb}

Let's say you ask Tolokers whether they prefer cats or dogs. Then you ask them to select their favorite breed, and this field is required.

It's possible that after selecting a breed, the Toloker changes their choice of animal, and you get this response: animal — cat, breed — dachshund.

View an example with an error in the sandbox.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/0Ho2_pzu3ttAor)

To fix this, add the code to clear the `breed` data when the `animal` choice changes:

```json
"plugins": [
  {
    "type": "plugin.trigger",
    "onChangeOf": {
      "type": "data.output",
      "path": "animal"
    },
    "action": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "breed"
      },
      "payload": {
        "$empty": true
      }
    }
  }
]
```

See the updated example with clearing by trigger.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/jknPjrTl3ttAqw)

{% include [contact-support](../_includes/contact-support.md) %}