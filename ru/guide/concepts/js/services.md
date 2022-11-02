# Сервисы для решения специфических задач

{% include [deprecate](../../../_includes/deprecate.md) %}

{% include [toloka-requester-source-html-editor-tb](../../_includes/toloka-requester-source/id-toloka-requester-source/html-editor-tb.md) %}

## Geolocation {#Geolocation}

Позволяет получить GPS-координаты исполнителя, если они доступны. В `TaskSuite` и `Task` доступен через `this.geolocation`.

Методы:

#### getCurrentPosition(success, error, options)

Повторяет функциональность [navigator.geolocation.getCurrentPosition()](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/getCurrentPosition).

#### watchPosition(success, error, options)

Повторяет функциональность [navigator.geolocation.watchPosition()](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/watchPosition).

## Storage {#Storage}

Сохранение данных на клиенте. В `TaskSuite` и `Task` доступен через `this.storage`.

Методы:

#### setItem(key, value, expiration)

Сохранить значение под определенным ключом. Параметры:

- `key` — ключ.

- `value` — значение. Может быть любого типа, сериализуется приведением к строке.

- `expiration` — дата истечения срока хранения (`Date` или `number`). По умолчанию 24 часа.

#### getItem(key)

Возвращает значение по ключу.

#### removeItem(key)

Удаляет значение по ключу.

## TaskInterface {#TaskInterface}

[Интерфейс задания](../../../glossary.md#task-interface). В `TaskSuite` и `Task` доступен через `this.taskInterface`.

Методы:

#### showInstructionPopup()

Открывает [инструкцию](../instruction.md).

#### toggleFullscreen()

Раскрывает задание на весь экран, если оно свернуто. Иначе свернет задание.

## Hotkey {#Hotkey}

Позволяет подписаться на нажатие клавиш. В `TaskSuite` и `Task` доступен через `this.hotkey`.

Метод:

#### on(event, handler, context)

Подписывает переданный обработчик на определенное событие. Отслеживает события из параметра `event`. Параметры:

- `event`:

    - `enter` — клавиша «ввод».

    - `esc` — клавиша «отмена».

    - `arrow-left`, `arrow-right`, `arrow-up`, `arrow-down` — стрелки.

    - `key` — буквенно-числовые клавиши. Обработчик (параметр `handler`) получит нажатую клавишу в качестве первого аргумента.

- `handler` — обработчик события.

- `context` — `this` для обработчика.

#### reset()

Отменяет все сделанные ранее привязки и переинициализирует сервис.

## ClientInfo {#clientInfo}

Позволяет получить информацию об устройстве, на котором выполняются задания. В `TaskSuite` и `Task` доступен через `this.clientInfo`.

Метод:

#### getClientInfo()

Возвращает информацию об устройстве, если исполнитель работает в мобильном приложении:

- `deviceModel` — модель мобильного устройства.

{% include [contact-support](../../_includes/contact-support-help.md) %}