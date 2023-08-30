# Воспроизвести аудио

{% include [deprecate](../../_includes/deprecate.md) %}

В этом разделе мы покажем, как [добавить аудиоплеер](#insert-to-interface) в интерфейс и как убедиться, что исполнитель этот файл [прослушал](#validate-listened).

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

## Добавить аудиоплеер в интерфейс {#insert-to-interface}

Чтобы вставить звуковой файл в интерфейс задания, добавьте в шаблон компонент [view.audio](../reference/view.audio.md). В свойстве `url` укажите прямую ссылку на файл (рекомендуем использовать формат MP3):
```json
{
  "type": "view.audio",
  "url": "https://example.com/audio.mp3"
}
```

Если ссылка на аудиофайл передается во [входных данных](work-with-data.md), в свойстве `url` используйте компонент `data.input`.

Чтобы аудио автоматически воспроизводилось повторно, в свойстве `loop` укажите `true`.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/XEZ8x7vX3tvMFk)

## Убедиться, что исполнитель прослушал аудио {#validate-listened}

{% list tabs %}

- Начал прослушивание

  Чтобы убедиться, что исполнитель запустил аудио и хотя бы начал его прослушивание, в свойстве `validation` используйте компонент `condition.played`.
  ```json
  {
    "type": "view.audio",
    "url": "https://example.com/audio.mp3",
    "validation": {
      "type": "condition.played"
    }
  }
  ```

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/dPVZ8NbB3tvMUV)

- Прослушал до конца

  Чтобы убедиться, что исполнитель завершил прослушивание аудио, в свойстве `validation` используйте компонент `condition.played-fully`.
  ```json
  {
    "type": "view.audio",
    "url": "https://example.com/audio.mp3",
    "validation": {
      "type": "condition.played-fully"
    }
  }
  ```

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/Blk2vHHY3tvMby)

{% endlist %}

## Записать аудио {#record-audio}

Чтобы дать возможность исполнителю загружать свои аудиофайлы, используйте компонент [field.audio](../reference/field.audio.md).

Если исполнитель выполняет задание на сайте, то `field.audio` позволит загрузить файл, а если в приложении — откроет режим записи звука.

```json
{
  "type": "field.audio",
  "data": {
    "type": "data.output",
    "path": "path",
  }
}
```

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/uDWbPPCP3ttFAM)

## Создать задание, в котором нужно превратить аудио в текст {#transform-to-text}

Чтобы создать шаблон для задания по транскрибации аудио, мы использовали следующие компоненты:

- [condition.played](../reference/condition.played.md) — чтобы убедиться, что исполнитель прослушал аудио;
- [condition.required](../reference/condition.required.md) — чтобы убедиться, что исполнитель ввел текст в многострочное поле ([field.textarea](../reference/field.textarea.md));
- [plugin.toloka](../reference/plugin.toloka.md) — чтобы настроить внешний вид задания.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/OW1mnada3tvMrT)

[![](../_images/buttons/contact-support.svg)](../concepts/support.md)