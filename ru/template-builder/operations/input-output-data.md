# Чтение и запись

В этом разделе показаны примеры чтения из входных данных (`data.input`) и записи в выходные данные (`data.output`).

Чтение и запись в промежуточные данные (`data.internal`) осуществляется таким же образом.

О том, как ввести внутри объекта во входных данных кавычки вида `"`, обратную косую черту `\`, перенос строки или табуляцию, читайте в разделе [Если вы не знакомы с JSON](../quickstart.md). Об  экранировании в TSV-файле читайте в [Руководстве заказчика]({{ toloka-requester-create-tsv }}).

## Простой пример {#read-write-data}

Допустим, вы хотите вывести текст с вопросом из входных данных и записать ответ в выходные данные. Пример входных данных:
```json
{
  "question": "А вы купили бы слона?"
}
```
Пример отображения вопроса в компоненте [view.text](../reference/view.text.md):
```json
{
  "type": "view.text",
  "label": "Ответьте на вопрос:",
  "content": {
    "type": "data.input",
    "path": "question"
  }
}
```
Пример записи ответа с помощью компонента [field.radio-group](../reference/field.radio-group.md):
```json
{
  "type": "field.radio-group",
  "options": [...],
  "data": {
    "type": "data.output",
    "path": "verdict"
  }
}
```

Когда вы ответите положительно и нажмете **Отправить**, результат будет таким:

```json
{
  "output": {
    "verdict": true
  }
}
```

[Посмотреть пример в песочнице](https://clck.ru/Qi9VF).

## Чтение входных данных с типом JSON {#read-json}

Если во входных данных вы передаете JSON-объект и хотите получить значение для какого-то вложенного ключа, то укажите путь к нему, используя точку в качестве разделителя.

Допустим, во входных данных у вас есть объект, описывающий адрес регистрации.
```json
{
    "name": "Ivan Ivanov",
    "registration_аddress": {
        "country": "Russia",
        "city": "Moscow",
        "address": "Tverskaya str, 3-53"
    },
    ...
```

Чтобы отобразить в интерфейсе значение из свойства city, укажите путь к нему через точку:
```json
{
  "type": "data.input",
  "path": "registration_аddress.city"
}
```

[Посмотреть пример в песочнице](https://clck.ru/QiC9S).

## Запись данных с типом JSON {#write-json}

Аналогично осуществляется запись в выходные данные. Если вы укажете путь через точку, то в спецификации поле с выходными данными будет иметь тип объект.

[Посмотреть пример в песочнице](https://clck.ru/QiEt3).

## Чтение данных с типом "массив" {#read-array}

{% include [array-read-images-from-array](../_includes/operations/insert-images/id-array/read-images-from-array.md) %}


Если длина массива неизвестна или он очень большой, вы можете получить все значения массива с помощью компонента [helper.transform](../reference/helper.transform.md).

Например, вы можете преобразовать массив ссылок на изображения в массив компонентов [view.image](../reference/view.image.md), чтобы отобразить их в интерфейсе.

[Посмотреть пример в песочнице](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNlTE48jFmzwALItxYAnTnW0BDKHxgRtU4aIV4J02SkpWFtZawd4AJgboHOcKEwAroIgItTOeEzeaqogcFIGCET2TjQAvmERcVB0EHKpYkrMbhR4HCR+CUmW4dYggdrc+bVZrrFePjwQYAZNoQV1UXQx7nGSFiADOGkDM7Vz05hpodlBdChoVjZVyWwA2qnqdHRMfMgA9OdgHlCcAt0A1nxQBkx+EOfxCAC0w4FSACM+OcAJwANgADCRznwGjAiNpviQDPgiAB9ADMABEAEIAeQAmjiAAo4jEADU4ACsmAgaoUQGpjqcLlcbndcmAni83nAPl9fmp-kDQZDofA+BpzEZvnw4Nw1BBAkRjuiAKoAQSxaoAMgAlPUACQAogBpam0+k0I4nM6Xa63e5c56vd6fKQ-P6A4HgqHnCDcDzfJiK3JogDixoAigAmADseIA6gAtABqqYtdMm1AAuksQGkgA).

## Запись данных с типом "массив" {#write-array}

По аналогии с чтением элементов из массива, вы также можете записывать результаты в виде массива. Для этого укажите в свойстве `path` путь к массиву и номер элемента, начиная с нуля. Например:
```json
{
  "type": "data.output",
  "path": "images.0"
}
```

[Посмотреть пример в песочнице](https://clck.ru/QiCPA).

## Узнайте больше

- [Создание спецификации](create-specs.md)
- [Очистка введенных значений](clear-data.md)

[![](../_images/buttons/contact-support.svg)](../concepts/support.md)
