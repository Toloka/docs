# Настройка отображения заданий

Для управления настройками отображения заданий на странице используйте плагин `plugin.toloka`:
```json
{
  "type": "plugin.toloka",
  "layout": {
    "kind": "scroll",
    "taskWidth": 300
  }
}
```

Способы отображения задаются в свойстве `kind`:

- `scroll` (по умолчанию) — отображать несколько заданий на странице одновременно.
- `pager` — отображать на странице только одно задание, но внизу под заданием будет переключатель между заданиями.

С помощью свойства `taskWidth` вы можете настроить ширину задания. По умолчанию задание отображается на полный экран.


## Примеры {#concept_gqw_zr5_wlb}

#### Расположить несколько заданий в ряд

Допустим, вы хотите отображать по 2 задания в каждой строке на экране. Для этого поставьте значение `taskWidth` таким, чтобы на большинстве экранов у исполнителей помещалось 2 задания. Например, укажите значение `500`, чтобы на всех экранах с шириной больше 1000 пикселей отображалось по 2 задания. В свойстве `kind` значение `scroll`.

[Посмотреть пример в песочнице](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBuAhgE4DOeyWG2OuIAnoVACYCmAHhVZrbXgC70ADqy54AFqwA2I4gDpSrEmHEBaAI4BXVsXp4AND151WUBHCiiUdRiw4GjvPFp17r1Y3xCCRYkM0J+QjkLIU1+BxpPPCFA8T8XXQB9fg4IkEdaAF9MrMMougQICAQpK0oPYwFhcrpJGR0FJWIVDW1dSOiQRLcKzKdvGr8AoJCoMPT8zxwYuIT2+hS0vH6sPNW8U3NLPyKSspWCnJp1mjx8OFYAdy5KmcHfa3PLq7kpOFJJzLw4VIBbcjWADaqzuVQetWe1zehAARtJWMxVO9Pp1png-hYAOpwZj8eLWAAMU3RIF+rABXBBBU8YOmdCkcOkfkA6CCABhBAPwggAEQQB8IIBBEGQaPp90gUFSYtuq3p1UelChrz+JAA1swIFcoELhSLoOL0n0aVq6D5ISB6rI5AArCAWTWGujkynAqWGvAAKldtrt3ANXqNQye-kCwVC4U9vtm+PmriW7HSzq1p19A3dhyTWAAuiTwyBYb06Kmvcc7UXhYnhXTSYz4VI-IACEEArCCAZhBABwgPMAvCCCkBZ4V4UW6yU+0nGvwXaGpWNh0l90x671pmUms2NK02rvx0kOwGUalpnAV7PDgMjYPjUNrwd2iMEuXdBZJYisczQJJQQh-Kzr+ll+cgLAACknLV9y9BdhiDMYJkAl0QFiSMAx6JJIE0MUOgyC9S27bMAEoC19TNP3BXM-Fww0SwTdcyOMdNVm-WhgNAgNR1eFEvkHPBmDgB8wH4OBoD8cQIGIOAAC8dUIGtz2lMl-i3LAd3LAiGJvJi5EIbjeKgVRYXCfg+Mk6Cq2ZANAHwQHlmz5QAuECwQAmECwQB6EDbQAWEHrCy+Sg+41J4vT9QPf0b08jS5AgERNPeKAlXcrxYnoKQIEIZgBx-AASB8YBHEhSDkWw2E4NDfUor8KMw4xgIGQ9lJeVT1OgLSdL04qukMiSb1M8yrNsgBxYpSisBrwQC7y5xAiE-AGqAgpC5ELAi-TLxgwgYrihL3AIgYUtYNLGIyuQ9h6kjyPQnACuMY6cGog1aL3Z0lLoeBpGYORiHi3jVAQYgIE0IRJzwJrWU5Xk+SwCyeUAHhAQfrLlAHEQetLObQBOECwZtAG4QZssDbetACEQAB+b6QGCryoFk+T6VKrxfoDQAsEFB8GoZhiz4ci85xO0Lh+GIFn0MukrFJAcmb0AXBAXOpiHodhuHGYIZnahgcTFAo518LYwMgkSnsRqPcCPv4SDZtJWDrzoSA-nfFo4HE-bsj6pn3hGDTVak8rDegDiCce1gtE4xELaOmjMnOo6SRiKRNG2InMgrPAAEZ7fBR28DGppWKk48Y66OPleCLWdb6+59b8I2TbAM2JOdLnc4W2L4tZ9nRAu4q8AAJlTrx04TxQk9JFOVvQm72M18Js-XK984gY2dCL828umMu6GiyvlsoGWpDluuNhAG5u4dvy6AT4LTCm8Lcbnpbm7W1L0rILKmBy721ho+uQFk+j1f86rxr30LpqPiuT83tX1s2spbau0DhT08MdLmvcYLB22HIAS-AlSsHoICXI3YI4v1njAiwchdKxSVIQT0P0Fpa1PnQJUFgF50FIGAd6UgJJW28IQUgSocR4gNgAVkJISX2RwjDnSyF2Mkp5+AoDQEYZwd5xyzjwBTQAwiAcmbBjQAMiBYD5EjdsbI0QSOjEhFCeY8C1n5HyZsgB5EC0beaMD4nxQBfG+E0gBiECRkokxbYeTWUsocARWQgA).

#### Показывать одно задание из нескольких

Вы можете показывать только одно задание из нескольких, а внизу добавить переключатель. Для этого в свойстве `kind` укажите значение `pager`. Если не задавать ширину задания, то оно будет развернуто на полный экран.

[Посмотреть пример в песочнице](https://ya.cc/t/x4l3vmrP3YCoHC).

[![](../_images/buttons/contact-support.svg)](../concepts/support.md)
