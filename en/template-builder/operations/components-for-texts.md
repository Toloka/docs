# Components for working with text

In this section, we will tell you how to [display text](#insert-text) and [add a text entry field](#field-text). We'll also tell you which components you can use to [change text](#text-transform).


## Display text {#insert-text}

Use the [view.text](../reference/view.text.md) component to display text in the task interface. In the `content` property, insert the required text or specify a component with the [data.*](work-with-data.md) type that returns the text.

{% list tabs %}

- From input data

  To use the text from the input data, use the `data.input` component.

  [View example in the sandbox](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0dRAHnXgA0mGrUhQeEtlVE48jFmzwATAIZ1VnOFCYBXASGHVReJuoAWS+nwMiaAXzuOo9wyG166KNHfk2rADIQAE5EALZYcEwAzroRyhAANiFY0XB0WKphRLYuIPZAA&locale=en).

- From output data

  To use the text from the output data, use the `data.output` component.

  [View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNnnhFuAE06SAHoJAjqqvNwCGAIx2aQAUSiSATlitQGWIybOqcPF0rOis2KgCaPHVWFFpg0M4IAFc6JlThFQC8JhCACwdfPCyxAF8SrFL-JQjs+mZYijwOEgMiY0zzJTxIFyIXcIqxaIaHBKsk1PS-IaiQXLoCuOj2k1nyrpwNsQBdRQ3S0xA4KGmUNEPSoA).

{% endlist %}

If you want to insert formatted text, see the instructions and samples in the [Text formatting](text-formatting.md) section.


## Add a text entry field {#field-text}

To add a text entry field, use the [field.text](../reference/field.text.md) component for single-line text and [field.textarea](../reference/field.textarea.md) component for multi-line text.


[View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNnnhFuAE06SAHoJAjqqvNwCGAIx2aQAZThQE3IgFpeUIlhdMAVzosbT1hFSU8XSs6KzYqVTE8dVYUWmjYzgggwJMzRJo8JhiACwc+FzdPb1SIsQBfOqx6-KUExOTmVIotYj0DImMrACciONMmnEtbezS8AFkA7jo4LxdffyCQvt1w80iQDPGKdoLOjTnDmKssnKC9gqmQYroyy6kllbWfPEnmpsa+wAuopAfVTCBNnQUGhwfUgA).

## Change text {#text-transform}

To change the text, such as all uppercase letters or insert a variable value, use the following components:

- [helper.text-transform](../reference/helper.text-transform.md): Changes the text case. To transform the text, use the `transformation` property with the appropriate value:
    - `uppercase`: Convert all letters to uppercase.
    - `lowercase`: Convert all letters to lowercase.
    - `capitalize`: Convert the first letter of the text to uppercase and all the subsequent letters to lowercase.

  [View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNnnhFuAE06SAHoJAjqqvNwCGAIx2aQAUSiSATlitQGWIybOqcPF0rOis2KgCaPHVWFFpg0M4IAFc6JlThFQC8JhCACwdfTPNskF0iGCtk7hMKPD4IKSIsABUiYzwssQBfLqxu-yUI0piHDhIDdr8+wJBrO24HPJ0WV0njAFo6V08+GAhXKSEfHag9g6kQuGgAXmSmVbArPljBi3BoSRdwmaj6ZlidRAy24q3WdC2p3Oh2KkVmCTCcWGcLUAIcCKSqXS0xKkRy+UKU06uKUA1+s22u32hyu0Ac90ez1iv16JLJJORSmiaLieHG4NhpXm9l5wJWRDWvkhVIux0pZ2plzo1ygN24EBIEqeL0F70gLiI3yR5NRGlFILBUvl0KkutKCJ+JPeo1FGJSaQyphNs1ydAKoqKIBN7JR0ShitpUAc6s1rm1zKd-T6IaGv25ZqB-MDby5c1sIqBFol4OlCtlJxlNOVtyeTAkVl4AC9XmmPgajRROc6eYXxZKpqWbXb3g7jYmxOnAfEQlZMR6cSifQSA0Sg+P+jnneGLpGHLX602E5FWaoTzQALqKVndUwgOBQbEoNA37pAA).

- [helper.replace](../reference/helper.replace.md): Lets you replace some parts of the string with other strings. To do this, use the `find` property for the replaced text and the `replace` property for the replacing text.

  [View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNnnhFuAE06SAHnQCGAJyInhKpXm4mARjs0gAolElmsJqAyxHBEBFqVTxdE1M2KlUxPHVWFFpw004IAFc6JgzrEJi8JgiACxcAnJiaMKIYEzTuQIo8AGqATR9dIkMsfm8sKVq6OCgIuGgTbiwASQAVLEgpAt8sBxM+Il0u7AAlNL4+OBNvKHWLBH5PNY3-QqIsADkiOmuzeyO+K4isCBIoN8eb1fMYEKWCIUFOUBuEBgV3+JikNyG8KE3jeJB04xWWHw5hGO0+UF4EKwTAgZlM3DebSwqzMhDARDeg2pRHwRDMY1m6Q8ZmIfE4WCm1058x8fikJkGpkGlOJZggUkGoLovXMAGsHsSIHsBtBLttdvtkVM0mZ1QxkQAhHTmPFUgDSJgAXiZVYUBD5+RNld1oJDoX8sPYzAgGcq5gteZcA-q9j5JjMqRMPGyId6jjs6GYGJw8DYxABfPNYfPBVTRPL0ZgJBoEYgkAwdQKliv2JzcFzXbgsMycCxMez0ij9kz0kEj4GrZNQUdMg4QkjE8wmBDspjFIJFnB4SBT+rKXKhSsaRJ4Tvd3tEYf0srlJIRKyJcu3tRVlzJEypDJZJub2wgAqPCUja5geSglr+W4gPARwuPyN7lHgfYDtWtA5pg6DoSAv6FqBOFiAAuooOH5kEICDN+KBoCR+ZAA).

- [helper.join](../reference/helper.join.md): Joins multiple strings into one string, separating them with spaces or commas.

  [View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOkgB6CQI6qryQoki2yqqxedaxS0AFkW4sATpwBWEOFGEVWzwJaVknBRNbHDwAdWcAQzosMCSiBAgPBiwAEwgiPlx0PECo6JtopXtmRwo8HKSEzn8mAFdDY0qqkCYk500QKASpRyDogF9OrtpivCwAIzdoBCw6CAB+ErKlAF0p6Lx5hgGtibGsSfOK03oagfg3HM4+NyIwDvOYkG4Exe4BgDCzggEBeWASWCGdDg0AS3BSrX4-kc+26TB+YCIwO4OSIHgGADkIHRnP4VvwsC9uG9JDlSgcQBAmNDoOEKJEutdKngfn8BgApBK9KAFIhYGAgulGT7dfBw1q1WjeJinSqXbZiLkM3luAYAMQ8RCgYGc4sl9OmWnlirwMHxIBlOHVnMdNB5v11TjwACEPBJ+KaJRApaiGXLuAqBvN7a7xjK9jL6o1rK7qhovSAGnQmhB2m0Phq3T0+gM+BARpxcUQmJXGs9Xu9Vao49sW2IdooW+MjCAWu0UGhFHghiMBgBlVp8UlbbvjIA).


[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)
