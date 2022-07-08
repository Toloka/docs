# Введение

API Толоки позволяет создавать или удалять customizable-проекты, максимально точно настраивать и получать их списки.  Если вы хотите использовать ready-to-go-проекты и выполнять операции с ними, см. подробности в документации [API ready-to-go-проектов](https://toloka.ai/ru/docs/toloka-apps/api/concepts/quickstart-api.html).

Вы можете выполнять основные задачи:

- настроить [проект](concepts/project.md) с описанием свойств заданий (внешний вид, поля ввода и т. д.);

- создать [пул заданий](concepts/pool.md);

- определить логику [отбора исполнителей](concepts/my_users.md), которые будут выполнять задания;

- загрузить [данные для заданий](concepts/tasks.md) (URL картинок, текст и т. д.);

- [получить](concepts/result.md) и [проверить](concepts/accept.md) ответы.

Запросы к API Толоки выполняются по протоколу HTTPS. Сервис возвращает данные в формате JSON.

Для отладки заданий в Толоке используется тестовая среда — [песочница](https://sandbox.toloka.yandex.ru). После отладки настройки проекта и пула можно без изменений использовать в боевой версии Толоки (изменив [URL запроса и OAuth-токен](concepts/access.md)).

## Следите за нами в социальных сетях

[![](_images/SocialNetwork/youtube.svg)]({{ toloka-youtube }})[![](_images/SocialNetwork/facebook.svg)]({{ toloka-facebook }})[![](_images/SocialNetwork/slack.svg)]({{ toloka-slack }})[![](_images/SocialNetwork/linkedin.svg)]({{ toloka-linkedin }})[![](_images/SocialNetwork/twitter.svg)]({{ toloka-twitter }})[![](_images/SocialNetwork/github.svg)]({{ toloka-github }})[![](_images/SocialNetwork/StackOverflow.svg)]({{ toloka-stackoverflow }})[![](_images/SocialNetwork/blog.svg)]({{ toloka-blog }})