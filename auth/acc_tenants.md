## Таблица: acc_tenants
#### Назначение таблицы: Хранение информации о том, кто "арендует" приложение. 
#### Стркутра таблицы 
<table style="height: 252px; width: 669px;">
<thead>
<tr style="height: 36px;">
<th style="text-align: center; height: 36px; width: 84.5125px;">Название поля</th>
<th style="text-align: center; height: 36px; width: 44.225px;">Ключ</th>
<th style="text-align: center; height: 36px; width: 107.488px;">Тип поля</th>
<th style="text-align: center; height: 36px; width: 138.788px;">Обязательность</th>
<th style="text-align: center; width: 103.238px;">Пример</th>
<th style="text-align: center; height: 36px; width: 156.35px;">Описание</th>
</tr>
</thead>
<tbody>
<tr style="height: 36px;">
<td style="text-align: center; height: 36px; width: 84.5125px;">id</td>
<td style="text-align: center; height: 36px; width: 44.225px;">PK</td>
<td style="text-align: center; height: 36px; width: 107.488px;">BIGINT</td>
<td style="text-align: center; height: 36px; width: 138.788px;">Да</td>
<td style="text-align: center; width: 103.238px;">1</td>
<td style="text-align: center; height: 36px; width: 156.35px;">Идентификатор записи</td>
</tr>
    <tr style="height: 36px;">
<td style="text-align: center; height: 36px; width: 84.5125px;">code</td>
<td style="text-align: center; height: 36px; width: 44.225px;">-</td>
<td style="text-align: center; height: 36px; width: 107.488px;">VARCHAR(5)</td>
<td style="text-align: center; height: 36px; width: 138.788px;">Да</td>
<td style="text-align: center; width: 103.238px;">VSK</td>
<td style="text-align: center; height: 36px; width: 156.35px;">Код тената</td>
</tr>
<tr style="height: 36px;">
<td style="text-align: center; height: 36px; width: 84.5125px;">name</td>
<td style="text-align: center; height: 36px; width: 44.225px;">-</td>
<td style="text-align: center; height: 36px; width: 107.488px;"> VARCHAR(300)</td>
<td style="text-align: center; height: 36px; width: 138.788px;">Да</td>
<td style="text-align: center; width: 103.238px;">Вск. Продажа договоров страхования</td>
<td style="text-align: center; height: 36px; width: 156.35px;">Наименование тената</td>
</tr>
<tr style="height: 72px;">
<td style="text-align: center; height: 72px; width: 84.5125px;">is_deleted</td>
<td style="text-align: center; height: 72px; width: 44.225px;">-</td>
<td style="text-align: center; height: 72px; width: 107.488px;"> BOOLEAN</td>
<td style="text-align: center; height: 72px; width: 138.788px;">Да</td>
<td style="text-align: center; width: 103.238px;">false</td>
<td style="text-align: center; height: 72px; width: 156.35px;">Флаг удаления. True - неактивный(удален), false - активный</td>
</tr>
<tr style="height: 36px;">
<td style="text-align: center; height: 36px; width: 84.5125px;">created_at</td>
<td style="text-align: center; height: 36px; width: 44.225px;">-</td>
<td style="text-align: center; height: 36px; width: 107.488px;">TIMESTAMP</td>
<td style="text-align: center; height: 36px; width: 138.788px;">Да</td>
<td style="text-align: center; width: 103.238px;">2025-11-20T15:30:00Z</td>
<td style="text-align: center; height: 36px; width: 156.35px;">Дата/время создания&nbsp;</td>
</tr>
<tr style="height: 36px;">
<td style="text-align: center; height: 36px; width: 84.5125px;">updated_at</td>
<td style="text-align: center; height: 36px; width: 44.225px;">-</td>
<td style="text-align: center; height: 36px; width: 107.488px;">TIMESTAMP</td>
<td style="text-align: center; height: 36px; width: 138.788px;">Нет</td>
<td style="text-align: center; width: 103.238px;">2025-11-20T15:30:00Z</td>
<td style="text-align: center; height: 36px; width: 156.35px;">Дата/время обновления&nbsp;</td>
</tr>
</tbody>
</table>

#### SQL для создания таблицы
~~~
CREATE TABLE IF NOT EXISTS acc_tenants (
    id BIGINT PRIMARY KEY DEFAULT nextval('account_seq'),
    code VARCHAR(250) NOT NULL,
    name VARCHAR(300) NOT NULL,
    is_deleted BOOLEAN NOT NULL DEFAULT FALSE,
    created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
~~~
### Логика загрузки данных
1. Операция INSERT (SQL)
2. Метод REST API: /tnts
#### Название метода: 
```
POST: /tnts
```
#### Назначние метода: Создание тената 
<p>Входные параметры&nbsp;</p>
<p>body:</p>
<table border="1" style="border-collapse: collapse; width: 100%; height: 216px;">
<tbody>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px; text-align: center;"><strong>Значение параметра</strong></td>
<td style="width: 12.5%; text-align: center;"><strong>Тип</strong></td>
<td style="width: 12.5%; text-align: center;"><strong>Обязательность</strong></td>
<td style="width: 50%; height: 18px; text-align: center;"><strong>Описание</strong></td>
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;"><span>code</span></td>
<td style="width: 12.5%;"><span>string</span></td>
<td style="width: 12.5%; text-align: center;"><span>Да</span></td>
<td style="width: 50%; height: 18px;">Код тената</td>
</tr>
    </tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;"><span>name</span></td>
<td style="width: 12.5%;"><span>string</span></td>
<td style="width: 12.5%; text-align: center;"><span>Да</span></td>
<td style="width: 50%; height: 18px;">Наименование</td>
</tr>
</tbody>
</table>
<p>Пример запроса:&nbsp;</p>
<pre>
 {
 "code": "VSK", 
 "name": "Вск. Продажа договоров страхования" 
  }
</pre>
<p>Выходные параметры:&nbsp;</p>
<table border="1" style="border-collapse: collapse; width: 100%; height: 216px;">
<tbody>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px; text-align: center;"><strong>Значение параметра</strong></td>
<td style="width: 12.5%; text-align: center;"><strong>Тип</strong></td>
<td style="width: 12.5%; text-align: center;"><strong>Обязательность</strong></td>
<td style="width: 50%; height: 18px; text-align: center;"><strong>Описание</strong></td>
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;"><span>code</span></td>
<td style="width: 12.5%;"><span>string</span></td>
<td style="width: 12.5%; text-align: center;"><span>Да</span></td>
<td style="width: 50%; height: 18px;">Код тената</td>
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;"><span>id</span></td>
<td style="width: 12.5%;"><span>string</span></td>
<td style="width: 12.5%; text-align: center;"><span>Да</span></td>
<td style="width: 50%; height: 18px;">Идентфиикатор тената</td>
</tr>
        </tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;"><span>name</span></td>
<td style="width: 12.5%;"><span>string</span></td>
<td style="width: 12.5%; text-align: center;"><span>Да</span></td>
<td style="width: 50%; height: 18px;">Наименование</td>
</tr>
</tbody>
</table>
<p>Пример ответа:&nbsp;</p>
<p>Успех, код ответа 201</p>
<pre>
 {
 "id":"1",
 "code": "VSK", 
 "name": "Вск. Продажа договоров страхования" 
  }
</pre>

### Название сценария: Создание тената
#### Триггер: Вызван метод POST /tnts
#### Сценарий (успешный):
<p>1.  Создать в табалице acc_tenants запись
<p>1.1. Поле id = сгенирировать уникальный идентфикатор</p>
<p>1.2. Поле code = записать значение из вход. параметра "code" </p>
<p>1.3. Поле created_at = время/дата текущая</p>
<p>1.4. Поле&nbsp;is_deleted = по умаолчанию false</p>
<p>1.5. Поле updated_at = NULL</p>
2. Вернуть ответ POST /tnts, где "id" =  уникальный идентфикатор из шага "1.1", "code" из шага "1.2"

### Логика получения данных
#### Название метода:
```
GET: /tnts
```
#### Назначние метода: Получение всех активных тенатов
Входные параметры
No parameters
Выходные параметры:
<table border="1" style="border-collapse: collapse; width: 100%; height: 216px;">
<tbody>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px; text-align: center;"><strong>Значение параметра</strong></td>
<td style="width: 12.5%; text-align: center;"><strong>Тип</strong></td>
<td style="width: 12.5%; text-align: center;"><strong>Обязательность</strong></td>
<td style="width: 50%; height: 18px; text-align: center;"><strong>Описание</strong></td>
</tr>
<tr>
<td style="width: 25%; text-align: center;"><span>Массив</span></td>
<td style="width: 12.5%; text-align: center;"><span>-</span></td>
<td style="width: 12.5%; text-align: center;"><span>-</span></td>
<td style="width: 50%; text-align: center;">-</td>
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px; text-align: center;"><span>name</span></td>
<td style="width: 12.5%; text-align: center;"><span>string</span></td>
<td style="width: 12.5%; text-align: center;"><span>Да</span></td>
<td style="width: 50%; height: 18px; text-align: center;">Наменование&nbsp;тената</td>
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px; text-align: center;"><span>id</span></td>
<td style="width: 12.5%; text-align: center;"><span>string</span></td>
<td style="width: 12.5%; text-align: center;"><span>Да</span></td>
<td style="width: 50%; height: 18px; text-align: center;">Идентфиикатор тената</td>
</tr>
</tbody>
</table>
<p>Пример ответа:&nbsp;</p>
<p>Успех, код ответа 200</p>
<pre>
[
 {
 "id":"1",
 "code": "VSK", 
 "name": "Вск. Продажа договоров страхования" 
  }
]
</pre>

### Название сценария: Получение всех активных тенатов
#### Триггер: Вызван метод GET /tnts
#### Сценарий (успешный):
<p>1. Выполнить запрос к таблице acc_tenants</td>

~~~
SELECT * FROM acc_tenants WHERE is_deleted = FALSE;
~~~

<p>2. Вернуть ответ GET /tnts, используя маппинг табл. acc_tenants.id= id метод /tnts, табл. acc_tenants.name = name, табл. acc_tenants.code = code метод /tnts </td>

