## Таблица: acc_clients
#### Назначение таблицы: Хранение информации о партнерах (клиентах) с настройками
#### Структура  таблицы 

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
    id BIGINT PRIMARY KEY,
    client_idvarchar(255) NOT NULL,
    default_account_id BIGINT,
    name VARCHAR(250) NOT NULL,
    is_deleted BOOLEAN NOT NUL DEFAULT FALSE,
    created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
~~~
### Важно: для всех операций должна быть роль у пользователя админская TNT_ADMIN или SYS_ADMIN
Описано здесь <p><a href="https://github.com/OlegSirik/PoliTechDoc/blob/main/auth/testScripts.md">PoliTechDoc/auth/testScripts.md at main &middot; OlegSirik/PoliTechDoc</a></p>

### Логика загрузки данных
#### Название метода: 
```
POST /tnts/{tenantCode}/clients
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
<td style="width: 25%; height: 18px;"><span>tenantCode</span></td>
<td style="width: 12.5%;"><span>string</span></td>
<td style="width: 12.5%; text-align: center;"><span>Да</span></td>
<td style="width: 50%; height: 18px;">
<p>Код тенанта</p>
<p></p>
</td>
</tr>
</tbody>
</table>
<p><em>*Комменатрий: значение&nbsp;tenantCode можно получить в таблице&nbsp;acc_tenants поле code.</em></p>
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
<p><a class="nostyle" href="https://app.swaggerhub.com/apis/insur/PoliTechAccounts/2#/tenant_admin/createClient"><span>/tnts<wbr />/VSK/clients</span></a>&nbsp;</p>
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
 "clientId": "SRAVNI", 
 "defaultAccountId": "3",
 "name": "СРАВНИ" 
  }
</pre>

### Название сценария: Создание клиента
#### Триггер: Вызван метод /tnts/{tenantCode}/clients
#### Сценарий :

1. Проверить, что заполнены обязательные параметры в теле запроса "clientId","name" и в параметре пути {tenantCode}. Если проверка пройдена, то перейти на шаг 2, иначе исключение 2а
2. Проверить уникальность клиента. Если clientId в таблице acc_clients НЕ сущесвтует, то перейти на след. шаг, иначе исключение 3а
~~~
SELECT * FROM acc_clients WHERE client_id= '<значение clientId>';
~~~
3. Проверить по tenantCode наличие тенанта в таблице acc_tenants. Если запись найдена, то перейти на шаг 4, иначе исключение 4а
~~~
SELECT * FROM acc_tenants WHERE code = '<значение tenantCode>';
~~~
<p>4 Создать в таблице acc_clients запись</p>
<p>4.1. Поле id = сгенерировать уникальный идентификатор </p>
<p>4.2. Поле tid =  ИД тенанта из таблицы acc_tenants поле id (найти по tenantCode) </p>
<p>4.3. Поле client_id= значение из вход. параметра "clientId" </p>
<p>4.4. Поле default_account_id = значение из вход. параметра  defaultAccountId </p>
<p>4.5. Поле name =  значение из вход. параметра name </p>
<p>4.6. Поле is_deleted = по умолчанию false</p>
<p>4.7. Поле created_at = время/дата текущая</p>
<p>4.8. Поле updated_at = NULL</p>
<p>5. Вернуть ответ POST/tnts/{tenantCode}/clients, где:
<ul>
<li>"id" = значение шаг 4.1 &nbsp;</li>
<li>"defaultAccountId" = значение шаг 4.4 &nbsp;</li>
<li>"clientId"= значение шаг 4.3 &nbsp;</li>
<li>"name" = значение шаг 4.5 &nbsp;</li>
</ul>

#### Исключение 
<p>2а Сформировать сообщение об ошибке </p>
<p>3а Сформировать сообщение об ошибке </p>
<p>4а Сформировать сообщение об ошибке </p>

### Логика обновления данных
#### Название метода: 
```
PATCH /tnts/{tenantCode}/clients/{clientId}
```
#### Назначние метода: Обновление данных партнера (клиента)

Входящие параметры
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
<td style="width: 25%; height: 18px;"><span>tenantCode</span></td>
<td style="width: 12.5%;"><span>string</span></td>
<td style="width: 12.5%; text-align: center;"><span>Да</span></td>
<td style="width: 50%; height: 18px;">
<p>Код тенанта </p>
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
<p><em>Комментарий: Значение tenantCode можно получить в таблице acc_tenants поле code, значение&nbsp;<span>clientId в таблице&nbsp;acc_clients поле client_id</span></em>

<p><span>body</span>:&nbsp;</p>
<table border="1" style="border-collapse: collapse; width: 100%; height: 216px;">
<tbody>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px; text-align: center;"><strong>Значение параметра</strong></td>
<td style="width: 12.5%; text-align: center;"><strong>Тип</strong></td>
<td style="width: 12.5%; text-align: center;"><strong>Обязательность</strong></td>
<td style="width: 50%; height: 18px; text-align: center;"><strong>Описание</strong></td>
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;">defaultАccountId</td>
<td style="width: 12.5%;"><span>string</span></td>
<td style="width: 12.5%; text-align: center;"><span>Нет</span></td>
<td style="width: 50%; height: 18px;">
<p>Код тенанта </p>
<p></p>
</td>
</tr>
<tr>
<td style="width: 25%;">name</td>
<td style="width: 12.5%;"><span>string</span></td>
<td style="width: 12.5%; text-align: center;"><span>Нет</span></td>
<td style="width: 50%;">
<p>Наименование партнера (клиента)</p>
</td>
</tr>
<tr>
<td style="width: 25%;">isDeleted</td>
<td style="width: 12.5%;"><span>bool</span></td>
<td style="width: 12.5%; text-align: center;"><span>Нет</span></td>
<td style="width: 50%;">
<p>Флаг удаления&nbsp;</p>
</td>
</tr>
</tbody>
</table>

<p>Пример запроса:&nbsp;</p>
<p>PATCH /tnts/VSK/clients/SRAVNI</p>
<pre> { 
 "name": "СРАВНИ.РУ"
  }
</pre>
<p>Выходные параметры:&nbsp;</p>

<p><span>body</span>:&nbsp;</p>
<table border="1" style="border-collapse: collapse; width: 100%; height: 216px;">
<tbody>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px; text-align: center;"><strong>Значение параметра</strong></td>
<td style="width: 12.5%; text-align: center;"><strong>Тип</strong></td>
<td style="width: 12.5%; text-align: center;"><strong>Обязательность</strong></td>
<td style="width: 50%; height: 18px; text-align: center;"><strong>Описание</strong></td>
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;">defaultАccountId</td>
<td style="width: 12.5%;"><span>string</span></td>
<td style="width: 12.5%; text-align: center;"><span>Нет</span></td>
<td style="width: 50%; height: 18px;">
<p>Код тенанта </p>
<p></p>
</td>
</tr>
<tr>
<td style="width: 25%;">name</td>
<td style="width: 12.5%;"><span>string</span></td>
<td style="width: 12.5%; text-align: center;"><span>Нет</span></td>
<td style="width: 50%;">
<p>Наименование партнера (клиента)</p>
</td>
</tr>
<tr>
<td style="width: 25%;">isDeleted</td>
<td style="width: 12.5%;"><span>bool</span></td>
<td style="width: 12.5%; text-align: center;"><span>Нет</span></td>
<td style="width: 50%;">
<p>Флаг удаления&nbsp;</p>
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
#### Триггер: Вызван метод /tnts/{tenantCode}/clients/{clientId}
#### Сценарий :
1. Проверить наличие кода тенанта из запроса ("tenantCode") в таблице acc_tenants поле code И проверить наличие клиент ИД из запроса (clientId) в таблице acc_clients поле client_id. Если запись найдена, то перейти на след. шаг, иначе исключение 2а 
~~~
SELECT
    t.id,              -- ID Арендатора
    c.id,              -- ID Клиента
    c.tid  -- Идентификатор связи (tid)
FROM
    acc_tenants t
JOIN
    acc_clients c ON t.id = c.tid 
WHERE
    t.code = 'VSK' AND c.client_id= 'SRAVNI'; -- фильтрация по конкретным ID записей. Вставляем tenantCode (=t.code) И clientId (=c.client_id)из запроса
~~~
2. Обновить данные в таблице acc_clients на основании запроса в разерезе конкретного ИД клиента. Маппинг для обновления:
<p>2.1 табл.acc_clients.default_account_id = defaultAccountId</p>
<p>2.2 табл.acc_clients.name = name</p>
<p>2.3 табл.acc_clients.is_deleted = isDeleted.</p>
<p>2.4 табл.acc_clients.updated_at = Время/дата текущая </p>
3. Верунть ответ:
<p><em>*в зависмости от переданных параметров</em></p>
<ul>
<li><span>defaultАccountId</span></li>
<li><span>name</span></li>
<li><span>isDeleted</span></li>
</ul> 

#### Исключение 
<p>2а Сформировать сообщение об ошибке </p>

### Логика получения данных
#### Название метода: 
```
GET /tnts/{tenantCode}/clients
```
#### Назначние метода: Получение всех партнеров (клиентов)

<p>Входные параметры&nbsp;</p>
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
<td style="width: 25%; height: 18px;"><span>tenantCode</span></td>
<td style="width: 12.5%;"><span>string</span></td>
<td style="width: 12.5%; text-align: center;"><span>Да</span></td>
<td style="width: 50%; height: 18px;">
<p>Код тенанта </p>
<p></p>
</td>
</tr>
</tbody>
</table>
<p>Выходные параметры&nbsp;</p>
<p><span>body</span>:&nbsp;</p>
<table border="1" style="border-collapse: collapse; width: 100%; height: 448px;">
<tbody>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px; text-align: center;"><strong>Значение параметра</strong></td>
<td style="width: 12.5%; text-align: center; height: 18px;"><strong>Тип</strong></td>
<td style="width: 12.5%; text-align: center; height: 18px;"><strong>Обязательность</strong></td>
<td style="width: 50%; height: 18px; text-align: center;"><strong>Описание</strong></td>
</tr>
<tr style="height: 46px;">
<td style="width: 25%; height: 46px;">Массив</td>
<td style="width: 12.5%; height: 46px;"><span>-</span></td>
<td style="width: 12.5%; text-align: center; height: 46px;"><span>-</span></td>
<td style="width: 50%; height: 46px;">
<p>-</p>
</td>
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;"><span>id</span></td>
<td style="width: 12.5%; height: 18px;"><span>string</span></td>
<td style="width: 12.5%; text-align: center; height: 18px;">Да</td>
<td style="width: 50%; height: 18px;">
<p><span>&nbsp;ИД партнера</span></p>
<p></p>
</td>
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;"><span>clientId</span></td>
<td style="width: 12.5%; height: 18px;"><span>string</span></td>
<td style="width: 12.5%; text-align: center; height: 18px;">Да</td>
<td style="width: 50%; height: 18px;"><span>client_id партнера</span></td>
</tr>
<tr style="height: 118px;">
<td style="width: 25%; height: 118px;"><span>defaultAccountId</span></td>
<td style="width: 12.5%; height: 118px;"><span>string</span></td>
<td style="width: 12.5%; text-align: center; height: 118px;">Да</td>
<td style="width: 50%; height: 118px;">
<p><span>Id портфеля, в который будут попадать договоры, если не указан целевой портфель</span></p>
</td>
</tr>
<tr style="height: 46px;">
<td style="width: 25%; height: 46px;"><span>name</span></td>
<td style="width: 12.5%; height: 46px;"><span>string</span></td>
<td style="width: 12.5%; text-align: center; height: 46px;">Да</td>
<td style="width: 50%; height: 46px;">
<p><span>Наименование партнера</span></p>
</td>
</tr>
<tr style="height: 46px;">
<td style="width: 25%; height: 46px;">isDeleted</td>
<td style="width: 12.5%; height: 46px;"><span>bool</span></td>
<td style="width: 12.5%; text-align: center; height: 46px;">Да</td>
<td style="width: 50%; height: 46px;">
<p>Флаг удаления</p>
</td>
</tr>
<tr style="height: 46px;">
<td style="width: 25%; height: 46px;">createdAt</td>
<td style="width: 12.5%; height: 46px;"><span>string</span></td>
<td style="width: 12.5%; text-align: center; height: 46px;">Да</td>
<td style="width: 50%; height: 46px;">
<p>Дата/время создания</p>
</td>
</tr>
<tr style="height: 46px;">
<td style="width: 25%; height: 46px;">updatedAt</td>
<td style="width: 12.5%; height: 46px;"><span>string</span></td>
<td style="width: 12.5%; text-align: center; height: 46px;">Да</td>
<td style="width: 50%; height: 46px;">
<p>Дата/время обновления</p>
</td>
</tr>
</tbody>
</table>
<p>Пример ответа:&nbsp;</p>
<p>Успех, код ответа 200</p>
<pre>
[
 {
 "id":"1",
 "clientId": "SRAVNI", 
 "name": "СРАВНИ",
 "defaultAccountId": "3",
 "isDeleted": false,
  "createdAt": "2025-11-20T15:30:00Z",
  "updatedAt": "2025-12-20T15:30:00Z"
  }
]
</pre>

### Название сценария: Получение всех партнеров (клиентов)
#### Триггер: Вызван метод GET /tnts/{tenantCode}/clients
#### Сценарий :
1. Проверить по tenantCode наличие партнеров в таблице acc_clients. Если запись НЕ найдена, то перейти на шаг 2, иначе исключение 2а
~~~
SELECT
    t.id AS tenant_id,
    t.code AS tenant_code,
    c.clients_id
FROM
    acc_tenants t
JOIN
    acc_clients c ON c.tid = t.id
WHERE
    t.code = 'VSK'; -- фильтрация по коду тенанта 'VSK' 
~~~
2. Получить данные из таблицы acc_clients, где указан определнный тенант tenantCode 
~~~
SELECT *
t.id,
t.client_id,
t.default_account_id,
t.name,
t.is_deleted,
t.created_at,
t.updated_at
FROM
    acc_clients c
JOIN
    acc_tenants t ON t.id = c.tid 
WHERE
    t.сode = 'VSK' -- фильтрация по коду тенанта
~~~
3. Выполнить маппинг
   <ul>
<li>acc_clients.id = id&nbsp;</li>
<li>acc_clients.client_id=&nbsp;clientId</li>
<li>acc_clients.default_account_id = defaultAccountId</li>
<li>acc_clients.name = name</li>
<li>acc_clients.is_deleted = isDeleted</li>
<li>acc_clients.created_at = createdAt</li>
<li>acc_clients.updated_at =&nbsp;updatedAt</li>
</ul>
5. Вернуть ответ

#### Исключение 
<p>2а Сформировать сообщение об ошибке </p>

