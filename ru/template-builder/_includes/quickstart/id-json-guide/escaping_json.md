
Чтобы добавить в строку кавычку вида `"` или обратную косую черту `\`, дополните их обратной косой чертой `\`. Кавычки вида `« »` и `/` экранировать не надо.

#### Примеры
**Входные данные:** `"\"Перед тем как излить душу, убедитесь, что \"сосуд\" не протекает\". \\Джордж Бернард Шоу"`

**Результат:** 
`"Перед тем как излить душу, убедитесь, что "сосуд" не протекает". \Джордж Бернард Шоу`


**Входные данные:** `"«Перед тем как излить душу, убедитесь, что «сосуд» не протекает». /Джордж Бернард Шоу"`

**Результат:** `«Перед тем как излить душу, убедитесь, что «сосуд» не протекает». /Джордж Бернард Шоу`