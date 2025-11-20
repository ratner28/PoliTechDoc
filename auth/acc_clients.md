## Таблица: acc_clients
#### Назначение таблицы: Хранение информации о партнерах (клиентах) с настройками
#### Стркутра таблицы 

<table style="width: 717px; height: 313px;">
<thead>
<tr style="height: 36px;">
<th style="text-align: center; width: 133.712px; height: 36px;">Название поля</th>
<th style="text-align: center; width: 44.225px; height: 36px;">Ключ</th>
<th style="text-align: center; width: 107.488px; height: 36px;">Тип поля</th>
<th style="text-align: center; width: 129.25px; height: 36px;">Обязательность</th>
<th style="text-align: center; width: 169.113px; height: 36px;">Пример</th>
<th style="text-align: center; width: 157.55px; height: 36px;">Описание</th>
</tr>
</thead>
<tbody>
<tr style="height: 36px;">
<td style="text-align: center; width: 133.712px; height: 36px;">tid</td>
<td style="text-align: center; width: 44.225px; height: 36px;">FK</td>
<td style="text-align: center; width: 107.488px; height: 36px;">BIGINT</td>
<td style="text-align: center; width: 129.25px; height: 36px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 36px;"><span>1</span></td>
<td style="text-align: center; width: 157.55px; height: 36px;">Внешний ключ для связи с таблицей&nbsp;acc_tenants</td>
</tr>
<tr style="height: 44px;">
<td style="text-align: center; width: 133.712px; height: 43px;">id</td>
<td style="text-align: center; width: 44.225px; height: 43px;">PK</td>
<td style="text-align: center; width: 107.488px; height: 43px;">BIGINT</td>
<td style="text-align: center; width: 129.25px; height: 43px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 43px;"><span>2</span></td>
<td style="text-align: center; width: 157.55px; height: 43px;">ИД партнера</td>
</tr>
<tr style="height: 72px;">
<td style="text-align: center; width: 133.712px; height: 72px;">client_id</td>
<td style="text-align: center; width: 44.225px; height: 72px;">-</td>
<td style="text-align: center; width: 107.488px; height: 72px;">VARCHAR(255)</td>
<td style="text-align: center; width: 129.25px; height: 72px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 72px;">SRAVNI</td>
<td style="text-align: center; width: 157.55px; height: 72px;">Значение из JWT токена</td>
</tr>
<tr style="height: 36px;">
<td style="text-align: center; width: 133.712px; height: 36px;">default_account_id</td>
<td style="text-align: center; width: 44.225px; height: 36px;">-</td>
<td style="text-align: center; width: 107.488px; height: 36px;">BIGINT</td>
<td style="text-align: center; width: 129.25px; height: 36px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 36px;"><span>3</span></td>
<td style="text-align: center; width: 157.55px; height: 36px;">id портфеля, в который будут попадать договоры, если не указан целевой портфель.</td>
</tr>
<tr style="height: 36px;">
<td style="text-align: center; width: 133.712px; height: 36px;">name</td>
<td style="text-align: center; width: 44.225px; height: 36px;">-</td>
<td style="text-align: center; width: 107.488px; height: 36px;">VARCHAR(250)</td>
<td style="text-align: center; width: 129.25px; height: 36px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 36px;">Сравни</td>
<td style="text-align: center; width: 157.55px; height: 36px;">Наименование</td>
</tr>
<tr style="height: 18px;">
<td style="text-align: center; width: 133.712px; height: 18px;">is_deleted</td>
<td style="text-align: center; width: 44.225px; height: 18px;">-</td>
<td style="text-align: center; width: 107.488px; height: 18px;">BOOLEAN</td>
<td style="text-align: center; width: 129.25px; height: 18px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 18px;">false</td>
<td style="text-align: center; width: 157.55px; height: 18px;">Флаг удаления. True - неактивный(удален), false - активный</td>
</tr>
<tr style="height: 18px;">
<td style="text-align: center; width: 133.712px; height: 18px;">created_at</td>
<td style="text-align: center; width: 44.225px; height: 18px;">-</td>
<td style="text-align: center; width: 107.488px; height: 18px;">TIMESTAMP</td>
<td style="text-align: center; width: 129.25px; height: 18px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 18px;"><span>&nbsp;</span><code dir="ltr" class="o8j0Mc" jscontroller="PR9Qj" jsuid="y3NKp_d">2025-11-18T15:30:00Z</code></td>
<td style="text-align: center; width: 157.55px; height: 18px;">Дата/время создания&nbsp;</td>
</tr>
<tr style="height: 18px;">
<td style="text-align: center; width: 133.712px; height: 18px;">updated_at</td>
<td style="text-align: center; width: 44.225px; height: 18px;">-</td>
<td style="text-align: center; width: 107.488px; height: 18px;">TIMESTAMP</td>
<td style="text-align: center; width: 129.25px; height: 18px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 18px;"><code dir="ltr" class="o8j0Mc" jscontroller="PR9Qj" jsuid="y3NKp_d">2025-11-20T15:30:00Z</code></td>
<td style="text-align: center; width: 157.55px; height: 18px;">Дата/время обновления&nbsp;</td>
</tr>
</tbody>
</table>
<p></p>

#### SQL для создания таблицы:
~~~
CREATE TABLE IF NOT EXISTS acc_clients (
    tid BIGINT NOT NULL REFERENCES acc_tenants(id),
    id BIGINT PRIMARY KEY DEFAULT nextval('account_seq'),
    client_id varchar(255) NOT NULL,
    default_account_id BIGINT,
    name VARCHAR(250) NOT NULL,
    is_deleted BOOLEAN NOT NUL DEFAULT FALSE,
    created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
~~~
### Логика загрузки данных
#### Название метода: 
```
POST /tnts/{tenantId}/clients
```
#### Назначние метода: Создание партнера (клиента)

<p>Входные параметры&nbsp;</p>
<p><span>path</span>:</p>
<table border="1" style="border-collapse: collapse; width: 100%; height: 216px;">
<tbody>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px; text-align: center;"><strong>Значение параметра</strong></td>
<td style="width: 12.5%; text-align: center;"><strong>Тип</strong></td>
<td style="width: 12.5%; text-align: center;"><strong>Обязательность</strong></td>
<td style="width: 50%; height: 18px; text-align: center;"><strong>Описание</strong></td>
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;"><span>tenantId</span></td>
<td style="width: 12.5%;"><span>string</span></td>
<td style="width: 12.5%; text-align: center;"><span>Да</span></td>
<td style="width: 50%; height: 18px;">
<p>Идентификатор тената</p>
<p></p>
</td>
</tr>
</tbody>
</table>
<p>*Комменатрий: значение&nbsp;<span>tenantId можно получить в таблице&nbsp;</span>acc_tenants поле id.</p>
<p>body:</p>
<table border="1" style="border-collapse: collapse; width: 100%; height: 144px;">
<tbody>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px; text-align: center;"><strong>Значение параметра</strong></td>
<td style="width: 12.5%; text-align: center; height: 18px;"><strong>Тип</strong></td>
<td style="width: 12.5%; text-align: center; height: 18px;"><strong>Обязательность</strong></td>
<td style="width: 50%; height: 18px; text-align: center;"><strong>Описание</strong></td>
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;"><span>clientId</span></td>
<td style="width: 12.5%; height: 18px;"><span>string</span></td>
<td style="width: 12.5%; text-align: center; height: 18px;"><span>Да</span></td>
<td style="width: 50%; height: 18px;"><span>client_id партнера</span></td>
</tr>
<tr style="height: 90px;">
<td style="width: 25%; height: 90px;"><span>defaultAccountId</span></td>
<td style="width: 12.5%; height: 90px;"><span>&nbsp;string</span></td>
<td style="width: 12.5%; text-align: center; height: 90px;"><span>Нет</span></td>
<td style="width: 50%; height: 90px;"><span>Id портфеля, в который будут попадать договоры, если не указан целевой портфель.</span></td>
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;"><span>name</span></td>
<td style="width: 12.5%; height: 18px;"><span>string</span></td>
<td style="width: 12.5%; text-align: center; height: 18px;"><span>Да</span></td>
<td style="width: 50%; height: 18px;"><span>Наименование партнера</span></td>
</tr>
</tbody>
</table>
<p>Пример запроса:&nbsp;</p>
<p><a class="nostyle" href="https://app.swaggerhub.com/apis/insur/PoliTechAccounts/2#/tenant_admin/createClient"><span>/tnts<wbr />/1/clients</span></a>&nbsp;</p>
<pre> {
 "clientId": "SRAVNI", 
 "name": "СРАВНИ", 
 "defaultAccountId": "3"
  }
</pre>
<p>Выходные параметры:&nbsp;</p>
<table border="1" style="border-collapse: collapse; width: 100%; height: 216px;">
<tbody>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px; text-align: center;"><strong>Значение параметра</strong></td>
<td style="width: 12.5%; text-align: center; height: 18px;"><strong>Тип</strong></td>
<td style="width: 12.5%; text-align: center; height: 18px;"><strong>Обязательность</strong></td>
<td style="width: 50%; height: 18px; text-align: center;"><strong>Описание</strong></td>
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;"><span>id</span><span><br /></span></td>
<td style="width: 12.5%; height: 18px;"><span>string</span></td>
<td style="width: 12.5%; text-align: center; height: 18px;"><span>Да</span></td>
<td style="width: 50%; height: 18px;"><span>&nbsp;ИД партнера</span></td>
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;"><span>clientId</span></td>
<td style="width: 12.5%; height: 18px;"><span>string</span></td>
<td style="width: 12.5%; text-align: center; height: 18px;"><span>Да</span></td>
<td style="width: 50%; height: 18px;"><span>client_id партнера</span></td>
</tr>
<tr style="height: 90px;">
<td style="width: 25%; height: 90px;"><span>defaultAccountId</span></td>
<td style="width: 12.5%; height: 90px;"><span>&nbsp;string</span></td>
<td style="width: 12.5%; text-align: center; height: 90px;"><span>Нет</span></td>
<td style="width: 50%; height: 90px;"><span>Id портфеля, в который будут попадать договоры, если не указан целевой портфель</span></td>
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;"><span>name</span></td>
<td style="width: 12.5%; height: 18px;"><span>string</span></td>
<td style="width: 12.5%; text-align: center; height: 18px;"><span>Да</span></td>
<td style="width: 50%; height: 18px;"><span>Наименование партнера</span></td>
</tr>
</tbody>
</table>
<p></p>
<p>Пример ответа:&nbsp;</p>
<p>Успех, код ответа 201</p>
<pre> {
 "id": "2",
 "defaultAccountId": "3",
 "clientId": "SRAVNI", 
 "name": "СРАВНИ" 
  }
</pre>

### Название сценария: Создание клиента
#### Триггер: Вызван метод /tnts/{tenantId}/clients
#### Сценарий :
1. Описать право для создания клиента. Спросить у ОЮ.
2. Проверить, что заполнные обязательные параметры в теле запроса "clientId","name" и в парамтре пути {tenantId}. Если проверка пройдена, то перейти на шаг 3, иначе исключение 3а
3. Проверить по tenantId наличие тената в таблице acc_tenants. Если запись найдена, то перейти на шаг 4, иначе исключение 4а
~~~
SELECT * FROM acc_tenants WHERE id = <значение tenantId>;
~~~
<p>4 Создать в таблице acc_clients запись</p>
<p>4.1. Поле id = сгенерировать уникальный идентификатор </p>
<p>4.2. Поле tid =  значение из вход. параметра "tenantId" </p>
<p>4.3. Поле client_id = значение из вход. параметра "clientId" </p>
<p>4.4. Поле default_account_id = значение из вход. параметра  defaultAccountId </p>
<p>4.5. Поле name = по умолчанию false</p>
<p>4.6. Поле is_deleted = по умолчанию false</p>
<p>4.7. Поле created_at = время/дата текущая</p>
<p>4.8. Поле updated_at = NULL</p>
<p>4. Вернуть ответ POST/tnts/{tenantId}/clients, где:
<ul>
<li>"id" = значение шаг 4.1 &nbsp;</li>
<li>"defaultAccountId" = значение шаг 4.4 &nbsp;</li>
<li>"clientId"= значение шаг 4.3 &nbsp;</li>
<li>"name" = значение шаг 4.5 &nbsp;</li>
</ul>
5. Вернуть ответ GET /tnts 

#### Иключение 
3а Сформировать сообщение об ошибке 
4а Сформировать сообщение об ошибке 

### Логика обновления данных
#### Название метода: 
```
PATCH /tnts/{tenantId}/clients/{clientId}
```
#### Назначние метода: Обновление данных партнера (клиента)

<p><span>path</span>:&nbsp;</p>
<table border="1" style="border-collapse: collapse; width: 100%; height: 216px;">
<tbody>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px; text-align: center;"><strong>Значение параметра</strong></td>
<td style="width: 12.5%; text-align: center;"><strong>Тип</strong></td>
<td style="width: 12.5%; text-align: center;"><strong>Обязательность</strong></td>
<td style="width: 50%; height: 18px; text-align: center;"><strong>Описание</strong></td>
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;"><span>tenantId</span></td>
<td style="width: 12.5%;"><span>string</span></td>
<td style="width: 12.5%; text-align: center;"><span>Да</span></td>
<td style="width: 50%; height: 18px;">
<p>Идентификатор тената</p>
<p></p>
</td>
</tr>
<tr>
<td style="width: 25%;"><span>clientId</span></td>
<td style="width: 12.5%;"><span>string</span></td>
<td style="width: 12.5%; text-align: center;"><span>Да</span></td>
<td style="width: 50%;">
<p>Идентификатор партнера (клиента)</p>
</td>
</tr>
</tbody>
</table>
<p><em>Комментарий: Значение tenantId можно получить в таблице acc_tenants поле id, значение&nbsp;<span>clientId в таблице&nbsp;acc_clients поле id</span></em>
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
<td style="width: 25%; height: 18px;"><span>defaultАccountId</span></td>
<td style="width: 12.5%;"><span>string</span></td>
<td style="width: 12.5%; text-align: center;"><span>Нет</span></td>
<td style="width: 50%; height: 18px;">
<p>Идентификатор тената</p>
<p></p>
</td>
</tr>
<p>Пример запроса:&nbsp;</p>
<p>PATCH /tnts/1/clients/2</p>
<pre> { 
 "name": "СРАВНИ.РУ"
  }
</pre>
<p>Выходные параметры:&nbsp;</p>
</p>
<tr>
<td style="width: 25%;"><span>name</span></td>
<td style="width: 12.5%;"><span>string</span></td>
<td style="width: 12.5%; text-align: center;"><span>Нет</span></td>
<td style="width: 50%;">
<p>Наименование партнера (клиента)</p>
</td>
</tr>
<tr>
<td style="width: 25%;"><span>isDeleted</span><span><br /></span></td>
<td style="width: 12.5%;"><span>bool</span></td>
<td style="width: 12.5%; text-align: center;"><span>Нет</span></td>
<td style="width: 50%;">
<p><span>Флаг удаления. True - неактивный(удален), false - активный</span></p>
</td>
</tr>
</tbody>
</table>
<p>Пример ответа:&nbsp;</p>
<p>Успех, код ответа 200</p>
<pre> {
 "name": "СРАВНИ.РУ" 
  }
</pre>

### Название сценария:  Обновление данных партнера (клиента)
#### Триггер: Вызван метод /tnts/{tenantId}/clients/{clientId}
#### Сценарий :
1. Проверить налчие ИД тената из запроса "tenantId" в таблице acc_tenants поле id И проверить налчие ИД клиента из запроса значение clientId в таблице acc_clients поле id. Если запись найдена, то перейти на след. шаг, иначе исключение 2а
~~~
SELECT
    t.id,              -- ID Арендатора
    c.id,              -- ID Клиента
    c.tid AS tid_tenat -- Идентификатор связи (tid)
FROM
    acc_tenants t
JOIN
    acc_clients c ON t.id = c.tid 
WHERE
    t.id = 1 AND c.id = 2; -- фильтрация по конкретным ID записей. Вставляем tenantId (t.id) И clientId (c.id )из запроса
~~~
2. Обновить данные в таблице acc_clients на основании запроса в разерезе конкретного ИД клиента. Маппинг для обновления:
<p>2.1 табл.acc_clients.default_account_id = defaultAccountId</p>
<p>2.2 табл.acc_clients.name = name</p>
<p>2.3 табл.acc_clients.is_deleted = isDeleted.</p>
<p>2.4 табл.acc_clients.updated_at = Время/дата текущая </p>
4. Верунть ответ:
<p><em>*в зависмости от переданных параметров</em></p>
<ul>
<li><span>defaultАccountId</span></li>
<li><span>name</span></li>
<li><span>isDeleted</span></li>
</ul> 

### Логика получения данных
#### Название метода: 
```
GET /tnts/{tenantId}/clients
```
#### Назначние метода: Получение всех партнеров (клиентов)


