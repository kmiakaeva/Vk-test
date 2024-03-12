## Описание проекта

Это React-приложение, разработанное в рамках профильного задания на позицию Frontend-разработчика в команду сообществ.

### Функциональность

Приложение предназначено для отображения списка групп, полученных с сервера. Для запроса данных используется замоканный ответ метода, загружаемый из файла groups.json. Сервер возвращает данные в следующем формате:

```tsx
interface GetGroupsResponse {
  result: 1 | 0;
  data?: Group[];
}

interface Group {
  id: number;
  name: string;
  closed: boolean;
  avatar_color?: string;
  members_count: number;
  friends?: User[];
}

interface User {
  first_name: string;
  last_name: string;
}
```

После получения списка групп приложение отображает их на странице в произвольном виде. Каждая группа представлена следующими данными: имя группы, аватарка, тип приватности (закрытая / открытая), количество подписчиков и количество друзей. При клике на количество друзей в блоке группы отображается список имен и фамилий каждого друга.

Над списком групп расположен набор фильтров, позволяющих выбрать нужные группы по типу приватности, цвету аватарки и наличию друзей в группе.

### Особенности

Backend обрабатывает все запросы с задержкой в 1 секунду, что было учтено при разработке.
Метод также может вернуть ошибку или не вернуть поле data, что также обработано в коде.

### Запуск проекта

Для запуска проекта потребуется установить npm и Node.js. Далее выполните следующие шаги:

1. Выполните команду для установки зависимостей.

```bash
npm i
```

2. Для запуска локального сервера разработки выполните команду.

```bash
npm run dev
```

3. Перейдите по адресу http://localhost:5173/ в браузере.
