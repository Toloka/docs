# Мониторинг товаров

{% include [deprecate](../../_includes/deprecate.md) %}

{% include [categorization-toloka-sandbox-for-conref](../_includes/concepts/categorization/id-categorization/toloka-sandbox-for-conref.md) %}

{% include [walk-walk-abstract](../_includes/concepts/walk/id-walk/walk-abstract.md) %}

{% include [walk-walk-abstract-decomposing](../_includes/concepts/walk/id-walk/walk-abstract-decomposing.md) %}

Возможно, для вашего проекта нужны дополнительные настройки, например, добавление новой кнопки со сценарием выполнения или добавление блока с прикреплением файлов. Подробнее об этом читайте в разделе [Примеры кастомизации](advanced-features.md).

Предположим, вам нужно провести мониторинг выкладки товаров на стеллаже в магазине.

Для этого создадим такое задание: исполнителю необходимо будет прийти по адресу, сфотографировать фасад магазина, внутри найти соответствующую категорию и сфотографировать стеллаж c товарами определенного бренда. Если товаров бренда нет, предоставить фотографии в качестве доказательств. Если по адресу нет нужного магазина, сфотографировать адресную табличку и  здание, где он должен находиться.

Чтобы запустить задания и получить ответы:

1. [Создайте проект](#project)
1. [Создайте пул заданий](#pool)
1. [Загрузите задания](#tasks_upload)
1. [Запустите пул и получите результаты](#launch)

## Создайте проект {#project}

{% include [toloka-requester-source-project-def](../_includes/toloka-requester-source/id-toloka-requester-source/project-def.md) %}

#### В интерфейсе:

1. Выберите пресет:

    1. {% include [toloka-requester-source-create-project](../_includes/toloka-requester-source/id-toloka-requester-source/create-project.md) %}

    1. Выберите пресет {% if locale == "ru-ru" %}**Аудит планограммы выкладки товаров в магазине**{% endif %}{% if locale == "en-com" %}**Audit of the planogram of products displayed in the store**{% endif %} в блоке {% if locale == "ru-ru" %}**Пешеходные задания**{% endif %}{% if locale == "en-com" %}**Spatial Crowdsourcing**{% endif %}.

1. Заполните общую информацию:

    1. Дайте проекту понятное название и краткое описание. Их увидят исполнители в списке доступных заданий.

    1. По желанию добавьте **Приватный комментарий**.

    1. Нажмите **Сохранить**.

1. {% include [toloka-requester-source-edit-interface](../_includes/toloka-requester-source/id-toloka-requester-source/edit-interface.md) %}

    {% list tabs %}

    - Конструктор шаблонов

      1. Интерфейс задания описывает, как будут расположены элементы задания.

          Для этого проекта воспользуйтесь {% if locale == "ru-ru" %}[готовым кодом](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOAQ25EAToJAjqqvJCiTrbKqrF51rFO2I7JADxNmHNS9A2JhR4gAgggMIggCwggBwggEIgWID8IIDcIIAMIIC8IIB8IIDMIIACICmAPCD5gNIgWIBMIEWAXCCpkRXRWLEZpSk5jWVY+SlZKYDsINFpgKwgeCpKAL6+Dk4AFtIuISBwsBBD5jRjwzj2E-TMs25cXj7r-iDcugBGRNyaIIC4ID1NadH99Rk5WY0ZgJwgL4DiILXIwiOOAC1iItlcmz8Th21wAJro6LpOAsmABXQ4rCwgJgIybXKC6KQuIFYEZHNaY5SU4HbDSuLTuTiwuCEWFGZaqCmqSFKaF0ubaTgHQHU2inC5XekgUKRHL9QCCIADTCSQUE7CSac44QikSj0SK-DScXQ8VLdLDYYYiHxZCASWTKVylDzHLTdgyuMzWey7Y7xmIXcctVLBcLlaK8OLLtdAFggKVi-XeOWigHkQF5NPJK-288CBMHBKmGtQwqXwxHIqBojFFvDG01zJiGCCw1FgEz28nZjYqt3XQVeuBswwc0ZdwtbYMCxm8KAAawNW1Rhklc0mdDoTD4yAA9NuGLoBAi4GBOFAiHRt3wAMzbugQbgQWe6bdMbdWgCOqOtkkM290ADZ-wAFgATgAJgABgARgADl0KCrwg2EAHYryvZDYQAVmQ3RkJg5CQOQiCYHQ-9OAAKyYBAFyxKw1SlQBCEHlIokgqFIsDSdjom6DJAEYQPJADYQfpHmeZJ0myPJCiKEcxCdAMe0nPYdF0Ns4GgABaM50TvKAaJzKMV1oQB8EH6OVInjQAZECweVSgyOoKgyV4Yk42JpPDKEQBUug1N0iENWLflaC8nzOD4c89KxHEGAfc11VFV1FLwAABfcoDZTx1LvB8n23MskQfMAj2gGSHDkrY8riotNRLOY8s4CB0SrCKtjra4SAgQxZyMAB9SAOuZAlJFtfyHT8MrXXwfRByK3yKEDBKatoKxmW86A9G4SUx1dZaJB820KAUeKaHmidFpBFaQo-VE4CtWFmo8yYFgLPA7gE-I4meTisAqTIEgqcIhCwH4Gl4koElM-pzNiKybLs77HJyZz4zcrbyp1SqqoWwK8DqhqN31dzMeOVqpXazqer6wwBoRa0SqLUaqvGhwTqxRKQBS3Q0qIDKssfZ8dtWqAmX4REoDAFxUaxR7wTmcoOJSQBREAyGIE3lKzzKSfoHKwDJ4j4wApEC12IUk4e6thgJspAxomAvddnUvSzL7z53KdR4CBCsFunDSZjy72tom+Ttuq9WrG3aBJuZKepobvbGyWcykXRPDYTCIP8nAGb8ABdDs-SOE6g77RkByHb2mcL3sQ0ZfQjDD2i8xl8c-bOkB4EuWFOC09cNMMc01PUhAm1RJgzZpAzrkAJBAil40yPrKZponSeJygSDIkgGR4026FJzK3rN-LwCAmEF-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-Ig6mMukjfeqBM3OwjC61vdvWS-0zq77U01So61uAIk20iyHC28a10t42esqz3CujXaut2uSmiqFXvbvI6eSrAZB0YYYDBp0WsEBBAAtXSqXerO2etVEfBoWMUm+o4WBBgPGUfPAWcBYUxOYPgMAJsDaM2JwA8WcAAdUHDfqwBgggnTkdGGAZl7xGFMHmErHRBQDQHQGHBWDwAJCJGuAQS1mxtcVwTTHQF0ZABUdYD0cBEUddHZ10AQDtlEK633EPG8hPEFMvBvEoZfDfEvW-CMD-EAlAkglgngkQhQjQgwmwlwnwkImIlIgoiomMeGDAwtA+TPkQQ0d4W6ChKSB0b0djvid0aGGVBMeJibBbAPzmHUYqE0ZSe0dwD0cbGbGLWybtFyZidzH6gWA22uEwkwk4GQjAkwkIhgjTivH-FQnaaEHQk4H-AghgjAjAhgkIjQhghgn-BgiGEUckZGCAA){% endif %} {% if locale == "en-com" %}[ready-made code](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOAQ25EAToJAjqqvJCiTrbKqrF51rFO2I7JADxNmHNS9A2JhR4AIIArgAmElgQMFh0ABZEWEzculAQCIa6UrHxTIYQkeFgdHxY0XxpugxEkVhw2EkpAhCGLipKAL6+Dk7JUi4hIE0wEHhdOL1TyuZKTszDblxePrM4eOkARkTcmiAAynTtKVC5RMjCG7RWQXY3m-RLB5G6dLqcTUzh6-MWICY70SB3OQ0m-xo3VmM0h9n6zw0ri07k40UIkSMENUsNU8IBzgO2k4a2ukKeOz2B1CkUiHT4fCuphuAWsRFsrnxCMJyJAbw+XygPz+fieQKSB10tPpshAN2hkNxSi5jkRyxRXHRcExhmxPT6YhV-jVRNRpOZ5NolP2vIACkUSmUsGB3kQEO0GEyDQtwIF2cE5qK1C9efzPt9fmSg3hxSDeYViqUTPKYd6cEanjyRsStTq9WIlYaWSbecTeFAANZRhHhQw2kaJOh0JiMgD0rYYugE7zgYE4UCIdFbfAAzK2TtwIBXdK2mK2OgBHcJEARGVu6ABsG4ALABOABMAAYAIwADl0x5Hh8iAHYRyOb5EAKw33Q30833c3w8wB8bzgAFZMAg1YAnc-oHAAMk0FYJBAqTpJk2S5PmUJpoG3IhtmqK6GUcDQAAtNsvwnFAoE+taByHIkugdFgDAQLWzoQO00TnJIsroU8uF0PhZGco8wZIiMPF8ZwfCDuRAJAgwk5Sg8lqqlmtAAAKdlAmKeARE5TjOYY8BALq8dAqE4lxxphgpQaZlhtD6YxzaRha1m0LGBwkO0FZGAA+pArFNK6sqCQqfiFj6+D6NqPYmQJilCeqvoaRIYn6Da5lPFY0TGVAsoUAocXpoJSm2ayWViYu4RwB0kRSaKeCJE0AZ4AAwrwYCwScWB8DRdEMUxfmGGxgW1X4eCWbFLnFcJdnvJ8DnCiNdWAsC7meT5A1DRxpmiiF1lhX4GaYdNeBqRkmnaRAk7Tq2mXJdAaL8B8UBgC46U+g1HIjH1WC0SkJzwTAtE-SQtRYDARR5C0WCTkZYmLQC4MQFIVmTTZx0gKdGlEFpOnXfpMPRfxRVocTmYTBNqPxa8s2CgtzmUzGK28htAVbXKBUkxzTxSLonhsE+h7E7tfgALopoq6GHYs6M5nAGJYuzZmzFLJbYVw+hGCKCLgZ9GGjartDwHskScMRTaETk0QQAR2SMUw8NWrouz1rQhx7EQTpQx8fCwZAUhpIOfGxEw2VeoJeAQCHfG5Vg+UuYdAKUbyACSYOMRpCTJFghiII2XXJNwMAO6qEXcMuBxTttSscwnFFO1SvKhKkDpJlgJASIkmf8Fg2w5Bn-BQAA5HQsTNFn3V7EX9MuVo+jl7ymTeRI0hV-qxO16qScjAAKuPJx0d3YCThJDTtFgUj8HwTQgdP1mz2XCWL+0N9C4JItvffUXZSj0YG6Vd1QE4BVKq9Ri60A+k1I47snTQBSHETOcCo7QEZM3Xsf1dAIDTuEDSQgsCZFQS9BIGDcH4ITI6OguC2h0SPhAE+nBV7TA-nyWaP8lrKTGjTeaTk3piiZtmIw0QygMKwMLNeloBjSASmMcmqZlbFnYSAAuLBDDiXbnQMAcZzKWC7CueQgkN63GgGVGKFADFowSrdbKnAiBLn0JxUmahyYjErrfX+41TEOPMdTAUXCtao0ZhKUsAjezJi5iIoWPDaD0nCNwAMZiqallRLwAQYCnjLxkHosJhUsnGgUcSHmhgKyRAgCQfikSwJ+l1ngAAVNU20iQIAnAqPAqGDkr6YnyAgrq+8iC1OEdXSmesGZ-wIKiApRSSllM8caHWkDqnb10F5LA+5UgNKaZ0qGVCiCDwqIjawYMIaVDgDAGARh-Q-SgAgAwFQ+DwSSO8Ro5QuqIGwGdPBFwfrUIMLRbgDAsCECvtsAwnBqn9LEYM+JU0Eplhgqkn0tYXb1SbC2ZA7YpB0AIrMgiPwgW9nEiOTg6lNL9kHK2JoAhDBJmjuOS6ulvJG24JEbykh-bpA4rOHOL1vLP28seby25vIbgIhfQBTBLlwtVLMg4ABRTwuQA5goLOUmgkLcklRAAyk2Qxoi6AIvAAwErjSly-nxVhgzpYWKMQAoBNjKrVUNaqCB1Imy4U7kwNZtCNl71OPQxWgyRHKtVLhF6IczXDPdY0pxCRKWsByYw6ZTx3FDPNSM+yvw6aBp9G5XkcApAID4PS3CUpOhxoDQm2gUgYm8QVa4OgMbpn7WsqqrxiSuDjOKaUh1hi2RVJALU+pkbmnxChkZN0Ho+l+tRo2oMzaElqx0O2yZXbWT3F5PMxZKRdBg1IM6Y+RACLhCYKswdXqUg5HahUJoXSOgGAivsiSeFoBdTuTREeUM9kj3aXA4dWde5vLIUmCoajO4tCqu8oYFyGiYg+HAbgl6KhHyID8v5AK4BAqICCxVnMIXlotaaLg5YqyuMmngBFBxGzNjbK2dFmLKkYpxW1fFhKzrYxJUOcldaqXIJpVdXQ9LiCMuZdIGo7KahP0MAgby+5+XCqaJwMVN9M0ZTozKuVrKS2DOnaKWdeHeSas4NquAur9WvVwwQSK-JTUU39XO7txjAHAPtcR-xijGrOo+Bo496yWlZ1He6QwDBfXlq07-YNRBQ3Wf9TGD1bBOOxpsyFpaSbZ0tpGGmxyfiovLUCSMXN+bfKun8wwLDSqzOVtiXAGtFA4sNszTpkZ+TaITM7c5u+iVV0jFqc1JGQxrB8AnbV6Z9W8ljKax2qZpaV0QTXcneIfVDBec9cUoeI87i6CvalLpA4XoMlon86RhgebZVwVKKDg51twawMkDomHJ2TUS3iMzCj9NrF+roZdzCPhhpcwo9LGby28Jy4YqQvXQkJYbQ4sWHNREDO08Tf+39Iu-wUZYsStq7FwqcFGvAi90mY8++9pHbXfucPTdw6ZAS4z8MGiErDMOHAPaiSuKt32jrQqSY9fH6SY5x0psN9VjXCnjY+1KtddSPVDq6W07U36ulbIGzkxnRZJsNdG0LpdrXf6i86wspZKyI3eZ-a0HpOyDmBDN3kaIJyzn7IyFclcz7M4PIkDcl5kHwObq+UhusKH+BoeBaCu7LklcqqewLjnlYPtkd5BRlFaKMVYoY3i0czGsaeDY2SnKnHH05R43SzVQnWWBQ5Wg7lEneX8sFbJ0V4rNdLW17QWV8qDVB72nVsP6N9OGeM7B0zKvjWWZMcm4ZKOrVWMc6Auvv8nWNxdZ5g3nqfPG59SV7DWWwsRY8aWsUMXa31tLSH1UyWAe2Y4T4snmWU3Zty3mgtgMXSYlX-GlX5Xq0t+q-vzT7eVcjbbWNjXSm3aHWtA-aEup6zohW46geg2OS-OMsauzWE2NmU2va66SyC+kum2E83A+ADuby56FYQGHczciYZQl6Y8rQHyfmHonAWAu8ZwFwkuUMAGZB+cjEjKPcKQiGyG-yfu6GtBAAQq0LWH9PBC6CHCIVtkQLnNsO0NfPnHsLgRUJ1N1CUk7m+lnCwSPN3B0KlH8hfAyNfLdjAThj-uHgRrClPjWHWORsilRjRonuELin2CnkSqxgOOxlnpSjnnwHntOPxsbIXiJiuLOIhBAGXpJtJtuNXvJrXoASgZAk3upqvofsPjPCMl3vUEZnqr3h9gPoTKzukaPklOPraiAjVFYfrDPiMKEHPm6mAUvhAZIEVkFgfvESABvnEiftFpGrFp-v6qkYmiwkTj9uqn9uTtvq5HwuILfgVs0R6E-mWi-lWpVu-tGuXIrt-sgarn-uri1u0Q3jUtUt1iDv6P1tAZsUNh3uzrsYgSLipmutvAFnBGDE0KfL8BbnLj0lgMJpOHUA7iQIkH8swS3E6APMPKPHLgXPEG8ggHLH9FnLobctgFeiOj1mcVgAABTjALbYzN5EC4IgmkHaE3KXTvEUJfGnB4LwSTiXJGBdR7CXZJDdxaGEnXYpAgwVD4KYi8C4EBa4Jny3JDDMmXI-FwZEAACUxhlxsB1xBwL22MHwuhH2x+kxumaWpOGWXagOVOwOoOix9OQYhpDgUOwewUb0BiCOVmW+ox6MqO906OcG+OJwoI4Rz8+OqpKaJO5+WplRxo1+7AwSQireoUES8OIA0SsShRPov+OgySl+S03OmSph2xsZBm-++xZmhxfauuKQGB4BxEsGbEmCZ8NQhCgJZyUuEmGQcAAAXoTGwTEg0LsJ8VgTLqSeoQgn8twT7mwSQI8qbrodwL8tSRoWctKV-lcWYZ3gJlqlkT3i3u0fkYjjaTZqfolPZjakuOUdqeAm5rPh5vUSeo0XwLWEUNgsWXwK0Qlu0Z0dGb-Avn0RsTeWZp6WueqTND6f9mqdlrqXgHlgWrROnBUcFu0a-qscsDVjKSmVlmmYupmSrtmWgZuotuAadjKAhK6LEAtgdkdkHFfAgNgMBlWQgDWfWdlKbuhSuBUA8lDP6H3C9BOZTKkXATcXGZYe0dHg2HYaitRgnnRtik4Yxq4Sxunh4ZnhSlxrnrjHxgXiysEb4YUKXjyqeDEQpvcT2okWpjWiYXznKXprOQZvOTkYuWZsudaWkSRiMvaQ5mUU5oAU8NUbQLUYeT9KhY0VRQyJhZINeQMbeWACGl0T+Y+Xvs+X5a+cMauamWMZqd+WuVMUDv+bMZ5UFG0WVisVVusfFsxVsbBeYQuhmUgVlkhdUgALJnTvAejMSnF9YK6TmynTlsXpl7FFUppIWyo1BXqAnAlZzPxkUNmHx7qnwLYGFXyinYlnx4nqa4IXn0kdBAhVS4I0InwCkLbfSQBNkravH9x0BSkXH1UwVenqoKneBvYqmRWWVFExVfkTHxWU4HB+z6khlt5mUWYFEjFWXFGbkT4VEOV7m9oADqOckgblj1-ovlmmEOYSppe0wUNwMNBYXQMNSoMYZccJOUyZoekIH5qN4Q6NJItK04tUWwtQDkrOeAFYbxBwfAYARQw5i0TgXYFYAN2oQOp4h4gsioXQu0UO3QpgowQovwKAaA6Auo8wOOFwBw28ipnx6ActIAYIrA8trxxs1wYtqouaGCCUseVGnY3YvEfY4lo4fhM4c4FUK4kghg64W4e4R4Z4F4V4t494j4L4b4H4X4P4f4gEwEatXQeAKVUtMtiMeQct-t0o1FodIAKtjKvt4tgIoJkC0t3gst8tWhkd0dv1otftvo-k7EuivIT4T4nAN4+4T4X4p4AsI4G4d4hdQgD4nAG4h4p4+4+4p4X494p4p4G4p4kwYtfN3QQAA){% endif %}, где уже настроена валидация и внешний вид задания.

          Исполнитель не сможет отправить задание, если:

          - его геолокация будет отличаться от заданной более, чем на 50 метров;
          - не выберет вариант выполнения задания с помощью одной из трех кнопок;
          - не загрузит необходимые фотографии;
          - не напишет комментарий в том случае, если магазин закрыт или отсутствует.

      1. {% include [toloka-requester-source-tb-input-output_1](../_includes/toloka-requester-source/id-toloka-requester-source/tb-input-output_1.md) %}

          В данном проекте:

          - Поля входных данных:
            - `name` — строка с названием магазина;
            - `image` — ссылка на фото товара;
            - `address` — строка с адресом задания;
            - `product` — строка с описанием объекта;
            - `coordinates` — координаты точки, куда должен прийти исполнитель.

          - Поля выходных данных:

            - `address` — строка с адресом задания;
            - `comment` — строка с комментарием, который может написать исполнитель;
            - `verdict` — строка со статусом выполнения задания;
            - `coordinates` — строка с координатами задания;
            - `imgs_around` — массив файлов, фотографии окружения, которые загрузит исполнитель;
            - `imgs_facade` — массив файлов, фотографии магазина, которые загрузит исполнитель;
            - `imgs_category` — массив файлов, фотографии стеллажа, которые загрузит исполнитель;
            - `worker_coordinates` — координаты исполнителя в момент исполнения задания, с включенной опцией **Текущее положение**;
            - `imgs_plate_or_address` — массив файлов, фотографии таблички с адресом, которые загрузит исполнитель.

      1. {% include [toloka-requester-source-new-name-description](../_includes/toloka-requester-source/id-toloka-requester-source/new-name-description.md) %}

      1. Нажмите **Сохранить**.

    - Редактор HTML/CSS/JS

      1. {% include [toloka-requester-source-interface-html-block](../_includes/toloka-requester-source/id-toloka-requester-source/interface-html-block.md) %}

          Блок **JS** используется для описания логики задания. Кроме того, основной контент данного задания заложен в **JS** для простоты редактирования.

          В логике шаблона заложено минимальное количество фотографий фасада, объекта, таблички с адресом. Когда нет объекта, то фотографий окружения на месте объекта. Если вы хотите поменять эти значения, то найдите все строчки и измените для каждого варианта выполнения задания минимальное количество фото:

          ```javascript
          if (solution.output_values.imgs_facade.length < 2)
          if (solution.output_values.imgs_category.length < 2)
          if (solution.output_values.imgs_around.length < 4)
          ```

          В этом проекте в переменной `texts` хранятся тексты для блока с информацией и тексты для трех вариантов выполнения задания: **Я нашел нужный стеллаж**; **Товара бренда нет на полке**; **Магазин закрыт или отсутствует**.

          В переменной `MAX_DISTANCE` указана максимальная удаленность от назначенной точки (по умолчанию в километрах), на которую может отойти исполнитель во время выполнения задания. Укажите подходящее для вас значение.

      1. В блоке **Спецификация данных** задаются поля входных и выходных данных.

          {% cut "Что такое входные и выходные данные?" %}

          {% include [toloka-requester-source-input-data](../_includes/toloka-requester-source/id-toloka-requester-source/input-data.md) %}

          {% include [toloka-requester-source-output-data](../_includes/toloka-requester-source/id-toloka-requester-source/output-data.md) %}

          {% endcut %}

          {% include [toloka-requester-source-html-specification](../_includes/toloka-requester-source/id-toloka-requester-source/html-specification.md) %}

          В данном проекте:

          - Поля входных данных:

            - `name` — строка с названием магазина;
            - `image` — ссылка на фото товара;
            - `address` — строка с адресом задания;
            - `product` — строка с описанием объекта;
            - `coordinates` — строка с координатами точки, куда должен прийти исполнитель.

          - Поля выходных данных:

            - `address` — строка с адресом задания;
            - `comment` — строка с комментарием, который может написать исполнитель;
            - `verdict` — строка со статусом выполнения задания;
            - `coordinates` — строка с координатами задания;
            - `imgs_around` — массив файлов, фотографии окружения, которые загрузит исполнитель;
            - `imgs_facade` — массив файлов, фотографии магазина, которые загрузит исполнитель;
            - `imgs_category` — массив файлов, фотографии стеллажа, которые загрузит исполнитель;
            - `worker_coordinates` — координаты исполнителя в момент исполнения задания, с включенной опцией **Текущее положение**;
            - `imgs_plate_or_address` — массив файлов, фотографии таблички с адресом, которые загрузит исполнитель.

      1. {% include [toloka-requester-source-new-name-description](../_includes/toloka-requester-source/id-toloka-requester-source/new-name-description.md) %}

      1. Нажмите кнопку ![](../_images/tutorials/image-segmentation/preview-button.svg) {% if locale == "ru-ru" %}**Предпросмотр задания**{% endif %}{% if locale == "en-com" %}**Preview task**{% endif %}, чтобы увидеть получившееся задание.

          {% note info %}

          В предварительном просмотре проекта отображается одно задание со стандартными данными. Количество заданий на странице вы сможете настроить далее.

          {% endnote %}

      1. {% include [toloka-requester-source-exit-preview](../_includes/toloka-requester-source/id-toloka-requester-source/exit-preview.md) %}

      1. Нажмите **Сохранить**.

      {% endlist %}

1. Напишите краткую и ясную инструкцию. Опишите в ней, что надо сделать, и приведите примеры.

    Вы можете подготовить инструкцию в формате HTML и вставить ее в редактор. Чтобы переключиться в режим HTML, нажмите **<>**.

    Инструкция для пешеходных заданий должна хорошо читаться на экране мобильного телефона.

1. {% include [toloka-requester-source-end-edit-new-interface](../_includes/toloka-requester-source/id-toloka-requester-source/end-edit-new-interface.md) %}

## Добавьте пул заданий {#pool}

Пул — это набор оплачиваемых заданий, которые одновременно выдаются исполнителям.

1. Откройте проект и нажмите **Добавить пул**.

1. Дайте пулу любое удобное название и описание. Они доступны только вам, исполнитель будет видеть только название и описание проекта.

1. В блоке **Аудитория** добавьте **Фильтры** для отбора исполнителей. Чтобы ваши задания были доступны в мобильных приложениях Толоки исполнителям, владеющих русским языком и находящихся в Москве, установите язык и регион.

    ![](../_images/tutorials/walk/region-by-ip.png)

1. В блоке **Цена** установите цену за задание, например 0,2 $. Для пешеходных заданий всегда добавляйте одно задание на страницу.

    {% cut "Что такое страница заданий?" %}

    На одной странице может отображаться одно или несколько заданий. Если задания простые, то можно добавлять 10–20 заданий на одну страницу. Не рекомендуем создавать длинные страницы, поскольку это снизит скорость загрузки данных у исполнителя.

    Исполнитель получит оплату, только если выполнил все задания на странице.

    Количество заданий на странице вы определите при [загрузке заданий](#smart-mixing).

    {% endcut %}

    {% cut "Как определить справедливую цену?" %}

    Общее правило формирования цены — чем больше времени исполнитель тратит на выполнение, тем выше цена.

    Вы можете зарегистрироваться в Толоке как исполнитель и узнать, сколько платят другие заказчики за задания.

    {% endcut %}

1. В блоке **Контроль качества** установите **Перекрытие** — количество исполнителей, которые должны выполнить задание. Для пешеходных заданий, как правило, 1.

1. В блоке **Контроль качества** включите опцию **Отложенная приемка** и укажите количество дней на проверку для параметра **Срок проверки**. Например, 7.

    {% cut "Что такое отложенная приемка?" %}

    [Отложенная приемка](offline-accept.md) позволяет вам просматривать [выполненные страницы заданий](../../glossary.md#completed-tasks) перед тем, как принять их и заплатить исполнителю. Задания, выполненные в несоответствии с инструкцией, можно отклонять. Максимальный срок проверки устанавливается в поле **Срок проверки**.

    {% endcut %}

1. В блоке **Дополнительные настройки** укажите **Время** на выполнение страницы заданий. Его должно быть достаточно для того, чтобы добраться до места, найти указанную точку и загрузить фотографии. Для пешеходных заданий рекомендуем устанавливать сутки — 86 400 секунд.

1. Сохраните пул.

## Загрузите задания {#tasks_upload}

{% include [toloka-requester-source-tsv-file](../_includes/toloka-requester-source/id-toloka-requester-source/tsv-file.md) %}

1. Нажмите кнопку {% if locale == "ru-ru" %}**Загрузить**{% elsif locale == "en-com" %}**Upload**{% endif %}. В открывшемся окне вы можете скачать шаблон файла.

    #### Использовать пример данных

    Если вы хотите посмотреть, как ваш проект будет выглядеть после запуска, но у вас еще нет заданий для разметки, вы можете загрузить в пул готовый пример данных.

    Нажмите {% if locale == "ru-ru" %}**Использовать пример данных**{% elsif locale == "en-com" %}**Use sample data**{% endif %} справа от надписи {% if locale == "ru-ru" %}**Прикрепите подготовленный файл с данными**{% elsif locale == "en-com" %}**Attach the prepared file with data**{% endif %}. Это позволит избежать дополнительных действий с файлами.

    После того, как вы поработали с примером данных и вас все устроило, подготовьте свои данные и загрузите их в пул.

1. Добавьте в него входные данные. Заголовок столбца с входными данными содержит слово `INPUT`. Для пешеходных заданий также нужно указать широту `AI:latitude` и долготу `AI:longitude` каждой точки. Координаты можно уточнить, например, в [Яндекс Картах]({{ ya-maps-object-search }}).

    ![](../_images/tutorials/audit-place/audit-download.png)

1. Загрузите задания.

1. Выберите {% if locale == "ru-ru" %}**Указать вручную**{% elsif locale == "en-com" %}**Set manually**{% endif %} и установите значение 1 в поле {% if locale == "ru-ru" %}**Кол-во заданий на странице**{% elsif locale == "en-com" %}**Number of tasks per suite**{% endif %}.

1. Нажмите кнопку {% if locale == "ru-ru" %}**Разделить задания на страницы**{% elsif locale == "en-com" %}**Combine tasks into suites**{% endif %}.

## Запустите пул и получите результаты {#launch}

1. Запустите пул, нажав кнопку ![](../_images/other/b-start-pool.svg).

1. Следите за выполнением в блоке **Статистика пула**.

1. Как только получены первые результаты, вы можете начинать проверку.

    Чтобы проверить задания, откройте пул и нажмите **Скачать результаты**. Чтобы скачать вложения, нажмите кнопку рядом ![Выпадающее меню](../_images/other/drop-down.svg) и выберите **Скачать вложения**.

    {% note info %}

    По истечении установленного срока проверки все ответы будут автоматически приняты вне зависимости от качества ответа.

    {% endnote %}

{% include [contact-support](../_includes/contact-support-help.md) %}