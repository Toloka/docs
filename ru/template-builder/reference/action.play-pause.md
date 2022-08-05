# action.play-pause

Компонент управляет воспроизведением аудио или видео. Он останавливает воспроизведение, если оно запущено, и запускает, если остановлено.

Например, этот компонент позволит запускать два видео одновременно.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/Tx-yXweI3YChre)

Еще вы можете останавливать или запускать проигрывание по какому-то событию ([plugin.trigger](plugin.trigger.md)) или по нажатию горячей клавиши ([plugin.hotkeys](plugin.hotkeys.md)).

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/aSNa6h-z3YCi9t)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "action.play-pause" | Задает тип компонента. ||
|| `view` | _ref_ | Указатель на компонент, который воспроизводит аудио или видео. ||
|#
