# action.play-pause

{% include [deprecate](../../_includes/deprecate.md) %}

Компонент управляет воспроизведением аудио или видео. Он останавливает воспроизведение, если оно запущено, и запускает, если остановлено.

Например, этот компонент позволит запускать два видео одновременно.

[![Посмотреть пример в песочнице](../_images/buttons/view-example.svg)](https://ya.cc/t/Tx-yXweI3YChre)

Еще вы можете останавливать или запускать проигрывание по какому-то событию ([plugin.trigger](plugin.trigger.md)) или по нажатию горячей клавиши ([plugin.hotkeys](plugin.hotkeys.md)).

[![Посмотреть пример в песочнице](../_images/buttons/view-example.svg)](https://ya.cc/t/8MU78BrT3tvNR7)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "action.play-pause" | Задает тип компонента. ||
|| `view` | _ref_ | Указатель на компонент, который воспроизводит аудио или видео. ||
|#
