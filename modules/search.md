# uAPI модуля «Поиск по сайту»

#### [GET] Поиск материалов

> Обязательные параметры: `query`

Особенности:

1. Чтобы получить данные материалов со страницы 2, необходимо добавить параметр `&page=N` (где `N` – номер страницы).
1. Если не найдено материалов, то вы получите ответ `{"error":{"msg":"По запросу ничего не найдено"}}`.

Пример запроса:

    $response = $request->get('/search', array(
        'query' => 'myword'
    ));

Пример ответа:

    {
       "page":1,
       "pages_list":"1",
       "per_page":10,
       "search_results":3,
       "results":[
          {
             "images":{
                "small":"http://s4.ucoz.net/games/_sf/19/s63195591.jpg",
                "full":"http://s4.ucoz.net/games/_sf/19/63195591.jpg"
             },
             "indextime":"2014-12-22 02:04:13",
             "url":"http://yoursite.ucoz.ru/stuff/multiuser/allody_onlajn/8-1-0-1981",
             "title":"Аллоды Онлайн",
             "id":1981,
             "category":{
                "name":"Многопользовательские",
                "url":"http://yoursite.ucoz.ru/stuff/8",
                "id":8
             },
             "description":"«Аллоды Онлайн» — сверх популярная отечественная фэнтези вселенная с 13 летней историей! Некогда единый мир был расколот магической субстанцией Астрала ..."
          },
          {
              //второй материал
          },
          {
              //третий материал
          }
       ]
    }

Расшифровка переменных ответа:

- `page` – [Число] – Номер текущей страницы
- `pages_list` – [Число] – Общее количество страниц в модуле
- `per_page` – [Число] – Количество материалов на страницу
- `search_result` – [Число] – Найденных материалов
- `results` – [Массив] – **Полученные материалы**
    - `images` – [Массив] – **Если у материала есть загруженные изображения**
        - `small` – [Строка] – Ссылка на превью-изображение
        - `full` – [Строка] – Ссылка на полное изображение
    - `indextime` – [Строка] – Дата и время индексации материала в модуле
    - `url` – [Строка] – Ссылка на страницу найденного материала
    - `title` – [Строка] – Название найденного материала
    - `id` – [Строка] – ID найденного материала
    - `category` – [Массив] – **Принадлежность материала к категории**
        - `name` – [Строка] – Название категории
        - `url` – [Строка] – Ссылка на категорию
        - `id` – [Число] – ID категории
    - `description` – [Строка] – Описание найденного материала

#### [GET] Поиск по сайту + теги

> Обязательный параметр: `query`, `t` (`1` – учитывать теги, `0` – не учитывать теги)

Особенности:

1. Чтобы получить данные материалов со страницы 2, необходимо добавить параметр `&page=N` (где `N` – номер страницы).
1. Если не найдено материалов, то вы получите ответ `{"error":{"msg":"По запросу ничего не найдено"}}`.

Пример запроса:

    $response = $request->get('/search', array(
        'query' => 'myword',
        't' => '1'
    ));

Пример ответа:

    {
       "page":1,
       "pages_list":"1",
       "per_page":10,
       "search_results":3,
       "results":[
          {
             "images":{
                "small":"http://s4.ucoz.net/games/_sf/19/s63195591.jpg",
                "full":"http://s4.ucoz.net/games/_sf/19/63195591.jpg"
             },
             "indextime":"2014-12-22 02:04:13",
             "url":"http://yoursite.ucoz.ru/stuff/multiuser/allody_onlajn/8-1-0-1981",
             "title":"Аллоды Онлайн",
             "id":1981,
             "category":{
                "name":"Многопользовательские",
                "url":"http://yoursite.ucoz.ru/stuff/8",
                "id":8
             },
             "description":"«Аллоды Онлайн» — сверх популярная отечественная фэнтези вселенная с 13 летней историей! Некогда единый мир был расколот магической субстанцией Астрала ..."
          },
          {
              //второй материал
          },
          {
              //третий материал
          }
       ]
    }

Расшифровка переменных ответа:

- `page` – [Число] – Номер текущей страницы
- `pages_list` – [Число] – Общее количество страниц в модуле
- `per_page` – [Число] – Количество материалов на страницу
- `search_result` – [Число] – Найденных материалов
- `results` – [Массив] – **Полученные материалы**
    - `images` – [Массив] – **Если у материала есть загруженные изображения**
        - `small` – [Строка] – Ссылка на превью-изображение
        - `full` – [Строка] – Ссылка на полное изображение
    - `indextime` – [Строка] – Дата и время индексации материала в модуле
    - `url` – [Строка] – Ссылка на страницу найденного материала
    - `title` – [Строка] – Название найденного материала
    - `id` – [Строка] – ID найденного материала
    - `category` – [Массив] – **Принадлежность материала к категории**
        - `name` – [Строка] – Название категории
        - `url` – [Строка] – Ссылка на категорию
        - `id` – [Число] – ID категории
    - `description` – [Строка] – Описание найденного материала
