# uAPI модуля «Мини-чат»

- [Сообщения и смайлы](#module-mchat-messages)

<a name="module-mchat-messages"></a>
### Сообщения и смайлы

#### [GET] Получить сообщения

> Обязательные параметры: отсутствуют

Пример запроса:

    $response = $request->get('/mchat', array(
        //без параметров
    ));

Пример ответа:

    [
       {
          "uid":2,
          "ip":"94.180.161.137",
          "avatar":"http://2093175133.uid.me/avatar.jpg",
          "name":"Dmitry",
          "pending":"no",
          "custom1":"Поле1",
          "message":"Сообщение",
          "username":"Dmitry",
          "add_date":"2015-01-20 02:18",
          "email":"",
          "custom2":"Поле2",
          "url":"",
          "id":1
       }
    ]

Расшифровка переменных:

- `uid` – [Число] – ID пользователя (автора сообщения)
- `ip` – [Строка] – IP адрес автора сообщения
- `avatar` – [Строка] – Ссылка на аватар автора сообщения
- `name` – [Строка] – Имя автора сообщения
- `pending` – [Строка] – Находится ли на модерации данное сообщение (`yes`/`no`)
- `custom1` – [Строка] – Значение дополнительного поля 1
- `message` – [Строка] – Текст сообщения
- `username` – [Строка] – Никнейм автора сообщения
- `add_date` – [Строка] – Время добавления сообщения
- `email` – [Строка] – Email автора сообщения (если добавил гость)
- `custom2` – [Строка] – Значение дополнительного поля 2
- `url` – [Строка] – Значение поля www
- `id` – [Строка] – ID сообщения

#### [POST] Добавить сообщение

> Обязательные параметры: `message`

Пример запроса:

    $response = $request->post('/mchat', array(
        'message' => 'Сообщение из API'
    ));

Пример ответа:

    {
       "uid":2,
       "ip":"94.180.161.137",
       "avatar":null,
       "name":"Dmitry",
       "pending":"no",
       "custom1":null,
       "message":"Сообщение из API",
       "username":"Dmitry",
       "email":"",
       "custom2":null,
       "url":"",
       "adddate":"Вторник 02:29"
    }

Расшифровка переменных:

- `uid` – [Число] – ID пользователя (автора сообщения)
- `ip` – [Строка] – IP адрес автора сообщения
- `avatar` – [Строка] – Ссылка на аватар автора сообщения
- `name` – [Строка] – Имя автора сообщения
- `pending` – [Строка] – Находится ли на модерации данное сообщение (`yes`/`no`)
- `custom1` – [Строка] – Значение дополнительного поля 1
- `message` – [Строка] – Текст сообщения
- `username` – [Строка] – Никнейм автора сообщения
- `email` – [Строка] – Email автора сообщения (если добавил гость)
- `custom2` – [Строка] – Значение дополнительного поля 2
- `url` – [Строка] – Значение поля www
- `add_date` – [Строка] – Время добавления сообщения

#### [PUT] Редактор сообщения

> Обязательные параметры: `id`, `message`

Пример запроса:

    $response = $request->put('/mchat', array(
        'id' => '1',
        'message' => 'Измененное сообщение из API'
    ));

Пример ответа:

    {
       "success":{
          "msg":"Изменения сохранены"
       }
    }

Возможные параметры к передаче:

- `pending` – [Строка] – Находится ли на модерации данное сообщение (`yes`/`no`)
- `custom1` – [Строка] – Значение дополнительного поля 1
- `message` – [Строка] – Текст сообщения
- `email` – [Строка] – Email автора сообщения (если добавил гость)
- `custom2` – [Строка] – Значение дополнительного поля 2
- `url` – [Строка] – Значение поля www

#### [DELETE] Удаление сообщения

> Обязательные параметры: `id`

Пример запроса:

    $response = $request->delete('/mchat', array(
        'id' => '1'
    ));

Пример ответа:

    {
       "success":{
          "msg":"Сообщение удалено"
       }
    }

#### [GET] Получить смайлы

> Обязательные параметры: отсутствуют

Пример запроса:

    $response = $request->get('/mchat/smiles', array(
        // без параметров
    ));

Пример ответа:

    [
       {
          "angel":":angel:"
       },
       {
          "bag":":bag:"
       },
       {
          "batman":":batman:"
       },
       {
       //и так далее
       }
    ]
