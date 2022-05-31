# helper.translate

Компонент для перевода элементов интерфейса на другие языки. Подробнее в разделе [Перевод интерфейса задания](https://toloka.ai/ru/docs/guide/concepts/project-languages.html#project-languages__interface-translate).

В те свойства, которые должны отображаться на разных языках, добавьте:

```
{
  "type": "helper.translate",
  "key": "<имя ключа>"
{
```

При добавлении свойства `key` появится поле для ввода текста этого ключа. Введите туда текст на исходном языке. На последнем шаге «Переводы на другие языки» добавьте переводы ключей для нужных языков.

Пример использования:

```
{
  "view": {
    "type": "view.image",
    "url": "https://yastat.net/s3/tb/static/file-examples/image/small.png",
    "label": {
      "type": "helper.translate",
      "key": "label-image"
    }
  }
}
```

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "helper.translate" | Задает тип компонента. ||
|| `key`<span style="color: red">\*</span> | _string_ | Ключ текстового свойства, для которого вы будете добавлять перевод на разные языки. ||
|#
