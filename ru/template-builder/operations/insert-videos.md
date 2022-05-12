# Вставить видео

В этом разделе описано, как [вставить видео](#insert-videos) и [убедиться, что пользователь его посмотрел](#condition.played).


## Вставить видео {#insert-video}

Чтобы добавить видеофайл в интерфейс задания, используйте компонент [view.video](../reference/view.video.md). В свойстве `url` укажите прямую ссылку на файл или компонент, который её возвращает. Чтобы подставить ссылку из входных данных, используйте компонент [data.input](work-with-data.md).

Если вы хотите добавить несколько видео на страницу, посмотрите примеры в разделе [Сравнить видеоклипы](sbs-video.md).

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

[Посмотреть пример в песочнице](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0hAJkRHgA0mGrQCuAJwA2bKqNqMWbPDwCGdVZzhQmYukJGi8TdQAtlBOHwEhDOAL41D9zPZCCQ23XRRp0EwzxefgtTOjomAGdkAHoY+CkiAFoiAA9VAFsmRMikyAzOBDg6UzEAIy0IGLFsiFUeSJiAJgAGAEYAdhiWgBZ4uESAfTTM7KJBgFkABR7BgDYelsGAZgmAcU4snrx-VxB7IA).

## Убедиться, что пользователь посмотрел видео {#condition.played}

{% list tabs %}

- Начал смотреть

  Чтобы убедиться, что пользователь запускал видео, в свойстве `validation` используйте компонент `condition.played`.

  [Посмотреть пример в песочнице](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0hAJkRHgA0mGrQA2AQwBGRMWzyB8EEB8IIH4QQAIgSwIwggYRBAnCCAhEECsIFkCCIGsAMIIHYQbVkC8IOcBsIOf2AZECyAuEFur3NgNWA8EH11c0AmEEAOEFcAbsE7Y0tzFW0Td3NAeRAscMAWEEMlTiERGjwAVwAnORRaAAs6OiYAZ2QAekb4MSIAWiIADwkAWyY2uvbIXs4EODpKoqlOOAhGooGICR46xoAmAAYARgB2Rs2AFha4NoB9br6BojOAWQAFQ7OANkPNs4BmW4BxTn7D-LUHB4fASMRwHgSOhzKBsKiiYH0ZisCp4SBQHgTGGcAYSBhEHh4Ao4AC+BTJUBJIEEIDgUCYRToKDQVJJQA).

- Посмотрел до конца

  Чтобы убедиться, что пользователь посмотрел видео полностью, в свойстве `validation` используйте компонент `condition.played-fully`.

  [Посмотреть пример в песочнице](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0hAJkRHgA0mGrQA2AQwBGRMWzyB8EEB8IIH4QQAIgSwIwggYRBAnCCAhEECsIFkDsIIAYQFdsCCIPsAcIPsAyIFkBMILcAsIIaVZbWQLwgZwDYQM0csQC4QX1VQ7SwAasA8EH11M1dHAG7BP2M3JQD3M0B5ECsnJVClX0BxEDNfW3zOIREaPABXACc5FFoACzo6JgBnZAB6QfgxIgBaIgAPCQBbJjG+8chZzgQ4Ok6mqU44CEGmhYgJHj7BgCYABgBGAHZBy4AWEbgxgH1puYWiN4BZAAVHm8AGyPS5vADMvwA4px5o96tQcHh8BIxHAeBI6HsoGwqKJkfRmKwOnhIFAeBscZwFhIGEQeOMYE0xGIGHgGjgAL4NHlQLkgQQgOBQJhNOgoNACrlAA).

{% endlist %}

[![](../_images/buttons/contact-support.svg)](../concepts/support.md)
