# Схема данных


<p align="center">
 <img width="1000px" src="pic01.jpg" />
</p>

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
<td style="text-align: center; width: 103.238px;">1111111111111111</td>
<td style="text-align: center; height: 36px; width: 156.35px;">Идентификатор записи</td>
</tr>
<tr style="height: 36px;">
<td style="text-align: center; height: 36px; width: 84.5125px;">name</td>
<td style="text-align: center; height: 36px; width: 44.225px;">-</td>
<td style="text-align: center; height: 36px; width: 107.488px;"> VARCHAR(250)</td>
<td style="text-align: center; height: 36px; width: 138.788px;">Да</td>
<td style="text-align: center; width: 103.238px;">PARTAPI</td>
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

#### SQL для создания таблицы:
~~~
CREATE TABLE IF NOT EXISTS acc_tenants (
    id BIGINT PRIMARY KEY DEFAULT nextval('account_seq'),
    name VARCHAR(250) NOT NULL,
    is_deleted BOOLEAN NOT NULL DEFAULT FALSE,
    created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
~~~
#### Логика загрузки данных:
1. Операция INSERT (SQL)
2. Метод REST API: /tnts
### Название метода: POST /tnts
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
<td style="width: 25%; height: 18px;"><span>name</span></td>
<td style="width: 12.5%;"><span>string</span></td>
<td style="width: 12.5%; text-align: center;"><span>Да</span></td>
<td style="width: 50%; height: 18px;">Наменование&nbsp;тената</td>
</tr>
</tbody>
</table>
<p>Пример запроса:&nbsp;</p>
<pre>
{
  "name": "PARTAPI"
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
<td style="width: 25%; height: 18px;"><span>name</span></td>
<td style="width: 12.5%;"><span>string</span></td>
<td style="width: 12.5%; text-align: center;"><span>Да</span></td>
<td style="width: 50%; height: 18px;">Наменование&nbsp;тената</td>
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;"><span>id</span></td>
<td style="width: 12.5%;"><span>string</span></td>
<td style="width: 12.5%; text-align: center;"><span>Да</span></td>
<td style="width: 50%; height: 18px;">Идентфиикатор тената</td>
</tr>
</tbody>
</table>
<p>Пример ответа:&nbsp;</p>
<p>Успех, код ответа 201</p>
<pre>
{
 "id":"1111111111111111",
 "name": "PARTAPI" 
}
</pre>

### Название сценария: Создание тената
#### Триггер: Вызван метод POST /tnts
#### Сценарий (успех):
<p>1.  Создать в табалице acc_tenants запись
<p>1.1. Поле id = сгенирировать уникальный идентфикатор</p>
<p>1.2. Поле name = записать значение из вход. параметра "name" </p>
<p>1.3. Поле created_at = время/дата текущая</p>
<p>1.4. Поле&nbsp;is_deleted = по умаолчанию false</p>
<p>1.5. Поле updated_at = NULL</p>
2. Вернуть ответ POST /tnts, где "id" =  уникальный идентфикатор из шага "1.1", "name" из шага "1.2"

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
<td style="text-align: center; width: 169.113px; height: 36px;"><span>9223372036854775807</span></td>
<td style="text-align: center; width: 157.55px; height: 36px;">Внешний ключ для связи с таблицей&nbsp;acc_tenants</td>
</tr>
<tr style="height: 44px;">
<td style="text-align: center; width: 133.712px; height: 43px;">id</td>
<td style="text-align: center; width: 44.225px; height: 43px;">PK</td>
<td style="text-align: center; width: 107.488px; height: 43px;">BIGINT</td>
<td style="text-align: center; width: 129.25px; height: 43px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 43px;"><span>5553372036854775807</span></td>
<td style="text-align: center; width: 157.55px; height: 43px;">Наименование тената</td>
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
<td style="text-align: center; width: 169.113px; height: 36px;"><span>5553372036854775807</span></td>
<td style="text-align: center; width: 157.55px; height: 36px;">id портфеля, в который будут попадать договоры, если не указан целевой портфель.</td>
</tr>
<tr style="height: 36px;">
<td style="text-align: center; width: 133.712px; height: 36px;">name</td>
<td style="text-align: center; width: 44.225px; height: 36px;">-</td>
<td style="text-align: center; width: 107.488px; height: 36px;">VARCHAR(250)</td>
<td style="text-align: center; width: 129.25px; height: 36px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 36px;">Сравни</td>
<td style="text-align: center; width: 157.55px; height: 36px;">Наименование</td>
</tr>
<tr style="height: 18px;">
<td style="text-align: center; width: 133.712px; height: 18px;">is_deleted</td>
<td style="text-align: center; width: 44.225px; height: 18px;">-</td>
<td style="text-align: center; width: 107.488px; height: 18px;">BOOLEAN</td>
<td style="text-align: center; width: 129.25px; height: 18px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 18px;">false</td>
<td style="text-align: center; width: 157.55px; height: 18px;"></td>
</tr>
<tr style="height: 18px;">
<td style="text-align: center; width: 133.712px; height: 18px;">created_at</td>
<td style="text-align: center; width: 44.225px; height: 18px;">-</td>
<td style="text-align: center; width: 107.488px; height: 18px;">TIMESTAMP</td>
<td style="text-align: center; width: 129.25px; height: 18px;">Нет</td>
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
    name VARCHAR(250),
    is_deleted BOOLEAN DEFAULT FALSE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
~~~
#### Логика загрузки данных:
### Название метода: POST /tnts/{tenantId}/clients
#### Назначние метода: Создание партнера (клиента) 

## Таблица: acc_clients
Назаначение: Создание клиентов с разграничением прав доступа  к данным ( портфели )
Стркутра таблицы 
<table style="height: 313px; width: 669px;">
<thead>
<tr style="height: 36px;">
<th style="text-align: center; height: 36px; width: 80.125px;">Название поля</th>
<th style="text-align: center; height: 36px; width: 44.225px;">Ключ</th>
<th style="text-align: center; height: 36px; width: 107.488px;">Тип поля</th>
<th style="text-align: center; height: 36px; width: 129.25px;">Обязательность</th>
<th style="text-align: center; width: 169.113px; height: 36px;">Пример</th>
<th style="text-align: center; height: 36px; width: 113.975px;">Описание</th>
</tr>
</thead>
<tbody>
<tr style="height: 36px;">
<td style="text-align: center; height: 35px; width: 80.125px;">id</td>
<td style="text-align: center; height: 35px; width: 44.225px;">PK</td>
<td style="text-align: center; height: 35px; width: 107.488px;">BIGINT</td>
<td style="text-align: center; height: 35px; width: 129.25px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 35px;">6663372036854775807</td>
<td style="text-align: center; height: 35px; width: 113.975px;">Идентификатор записи</td>
</tr>
<tr style="height: 36px;">
<td style="text-align: center; height: 36px; width: 80.125px;">tid</td>
<td style="text-align: center; height: 36px; width: 44.225px;">FK</td>
<td style="text-align: center; height: 36px; width: 107.488px;">BIGINT</td>
<td style="text-align: center; height: 36px; width: 129.25px;">
<p>Нет</p>
</td>
<td style="text-align: center; width: 169.113px; height: 36px;">9223372036854775807</td>
<td style="text-align: center; height: 36px; width: 113.975px;">Внешний ключ для связи с таблицей acc_tenants.id</td>
</tr>
<tr style="height: 18px;">
<td style="text-align: center; width: 80.125px; height: 18px;">client_id</td>
<td style="text-align: center; width: 44.225px; height: 18px;">-</td>
<td style="text-align: center; width: 107.488px; height: 18px;">BIGINT</td>
<td style="text-align: center; width: 129.25px; height: 18px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 18px;"></td>
<td style="text-align: center; width: 113.975px; height: 18px;"></td>
</tr>
<tr style="height: 72px;">
<td style="text-align: center; height: 80px; width: 80.125px;">parent_id</td>
<td style="text-align: center; height: 80px; width: 44.225px;">-</td>
<td style="text-align: center; height: 80px; width: 107.488px;">BIGINT</td>
<td style="text-align: center; height: 80px; width: 129.25px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 80px;"></td>
<td style="text-align: center; height: 80px; width: 113.975px;"></td>
</tr>
<tr style="height: 36px;">
<td style="text-align: center; height: 36px; width: 80.125px;">node_type</td>
<td style="text-align: center; height: 36px; width: 44.225px;">-</td>
<td style="text-align: center; height: 36px; width: 107.488px;">VARCHAR(10)</td>
<td style="text-align: center; height: 36px; width: 129.25px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 36px;"><span>ACCOUNT</span></td>
<td style="text-align: center; height: 36px; width: 113.975px;">
<p>Разрешения</p>
<p></p>
</td>
</tr>
<tr style="height: 18px;">
<td style="text-align: center; width: 80.125px; height: 18px;">name</td>
<td style="text-align: center; width: 44.225px; height: 18px;"></td>
<td style="text-align: center; width: 107.488px; height: 18px;">VARCHAR(250)</td>
<td style="text-align: center; width: 129.25px; height: 18px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 18px;">SRAVNI</td>
<td style="text-align: center; width: 113.975px; height: 18px;">Наименование</td>
</tr>
<tr style="height: 18px;">
<td style="text-align: center; width: 80.125px; height: 18px;">created_at</td>
<td style="text-align: center; width: 44.225px; height: 18px;">-</td>
<td style="text-align: center; width: 107.488px; height: 18px;">TIMESTAMP</td>
<td style="text-align: center; width: 129.25px; height: 18px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 18px;">2025-11-20T15:30:00Z</td>
<td style="text-align: center; width: 113.975px; height: 18px;">Дата / время созадния</td>
</tr>
<tr style="height: 36px;">
<td style="text-align: center; height: 36px; width: 80.125px;">updated_at</td>
<td style="text-align: center; height: 36px; width: 44.225px;">-</td>
<td style="text-align: center; height: 36px; width: 107.488px;">TIMESTAMP</td>
<td style="text-align: center; height: 36px; width: 129.25px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 36px;">2025-11-20T15:30:00Z</td>
<td style="text-align: center; height: 36px; width: 113.975px;">Дата / время обновления</td>
</tr>
</tbody>
</table>
<p></p>
<p>Справочные значения для поля node_type:</p>
<table border="1" style="border-collapse: collapse; width: 100%; height: 216px;">
<tbody>
<tr style="height: 18px;">
<td style="width: 50%; height: 18px; text-align: center;"><strong>Значение</strong></td>
<td style="width: 50%; height: 18px; text-align: center;"><strong>Описание</strong></td>
</tr>
<tr style="height: 18px;">
<td style="width: 50%; height: 18px;"><span>ROOT</span></td>
<td style="width: 50%; height: 18px;"><span>Админ платформы. Может создавать новые разделы (tenant).</span></td>
</tr>
<tr style="height: 18px;">
<td style="width: 50%; height: 18px;"><span>TENANT</span></td>
<td style="width: 50%; height: 18px;"><span>Админ раздела. Может создавать учетки клиентов и управлять настройкой ресурсов клиентов.</span></td>
</tr>
<tr style="height: 72px;">
<td style="width: 50%; height: 72px;"><span>CLIENT</span></td>
<td style="width: 50%; height: 72px;"><span>Админ группы, продуктовый менеджер и т.д. Может управлять учетками и правами в рамках своих групп</span></td>
</tr>
<tr style="height: 18px;">
<td style="width: 50%; height: 18px;"><span>GROUP</span></td>
<td style="width: 50%; height: 18px;"><span>Админ группы, продуктовый менеджер и т.д. Может управлять учетками и правами в рамках своих групп</span></td>
</tr>
<tr style="height: 18px;">
<td style="width: 50%; height: 18px;"><span>ACCOUNT&nbsp;</span><span><br /></span></td>
<td style="width: 50%; height: 18px;"><span>Продавцы. Могут видеть свои договоры и выполнять действия в рамках прав.</span></td>
</tr>
<tr style="height: 18px;">
<td style="width: 50%; height: 18px;"><span>SUB</span><span><br /></span></td>
<td style="width: 50%; height: 18px;"><span>Продавцы. Могут видеть свои договоры и выполнять действия в рамках прав.</span></td>
</tr>
<tr style="height: 36px;">
<td style="width: 50%; height: 36px;"><span>PRODUCT</span></td>
<td style="width: 50%; height: 36px;"><span>Продутовый менеджер. Управояет продуктовым конструктором.</span><span><br /></span></td>
</tr>
</tbody>
</table>

SQL для создания таблицы:

~~~
CREATE TABLE IF NOT EXISTS acc_accounts (
    id BIGINT PRIMARY KEY,
    tid BIGINT NOT NULL REFERENCES acc_tenants(id),
    client_id BIGINT REFERENCES acc_clients(id),
    parent_id BIGINT REFERENCES acc_accounts(id),
    node_type VARCHAR(10) NOT NULL,
    name VARCHAR(250),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
~~~
Логика загрузки данных:
1.

## Таблица:  acc_product_roles
Назанчение: Содержит привязку портфеля к продукту. Для каждого продукта задается список прав на действия, которые с ним можно проводить (чтение, расчет, создание договора, пролонгация и т.д.)
Структура таблицы 
<table style="height: 419px; width: 669px;">
<thead>
<tr style="height: 36px;">
<th style="text-align: center; height: 36px; width: 111.75px;">Название поля</th>
<th style="text-align: center; height: 36px; width: 44.225px;">Ключ</th>
<th style="text-align: center; height: 36px; width: 82.3625px;">Тип поля</th>
<th style="text-align: center; height: 36px; width: 129.25px;">Обязательность</th>
<th style="text-align: center; width: 169.113px; height: 36px;">Пример</th>
<th style="text-align: center; height: 36px; width: 156.337px;">Описание</th>
</tr>
</thead>
<tbody>
<tr style="height: 36px;">
<td style="text-align: center; height: 35px; width: 111.75px;">id</td>
<td style="text-align: center; height: 35px; width: 44.225px;">PK</td>
<td style="text-align: center; height: 35px; width: 82.3625px;">BIGINT</td>
<td style="text-align: center; height: 35px; width: 129.25px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 35px;">5553372036854775807</td>
<td style="text-align: center; height: 35px; width: 156.337px;">Идентификатор записи</td>
</tr>
<tr style="height: 36px;">
<td style="text-align: center; height: 36px; width: 111.75px;">tid</td>
<td style="text-align: center; height: 36px; width: 44.225px;">FK</td>
<td style="text-align: center; height: 36px; width: 82.3625px;">BIGINT</td>
<td style="text-align: center; height: 36px; width: 129.25px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 36px;">9223372036854775807</td>
<td style="text-align: center; height: 36px; width: 156.337px;">Внешний ключ для связи с таблицей acc_tenants.id</td>
</tr>
<tr style="height: 18px;">
<td style="text-align: center; width: 111.75px; height: 18px;">account_id</td>
<td style="text-align: center; width: 44.225px; height: 18px;">FK</td>
<td style="text-align: center; width: 82.3625px; height: 18px;">BIGINT</td>
<td style="text-align: center; width: 129.25px; height: 18px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 18px;">3333372036854775807</td>
<td style="text-align: center; width: 156.337px; height: 18px;">Внешний ключ для связи с таблицей acc_accounts.id</td>
</tr>
<tr style="height: 72px;">
<td style="text-align: center; height: 80px; width: 111.75px;">role_product_id</td>
<td style="text-align: center; height: 80px; width: 44.225px;">FK</td>
<td style="text-align: center; height: 80px; width: 82.3625px;">BIGINT</td>
<td style="text-align: center; height: 80px; width: 129.25px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 80px;"></td>
<td style="text-align: center; height: 80px; width: 156.337px;">Внешний ключ для связи с таблицей acc_accounts.id</td>
</tr>
<tr style="height: 36px;">
<td style="text-align: center; height: 36px; width: 111.75px;">role_account_id</td>
<td style="text-align: center; height: 36px; width: 44.225px;">FK</td>
<td style="text-align: center; height: 36px; width: 82.3625px;">BIGINT</td>
<td style="text-align: center; height: 36px; width: 129.25px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 36px;"></td>
<td style="text-align: center; height: 36px; width: 156.337px;">Внешний ключ для связи с таблицей acc_accounts.id</td>
</tr>
<tr style="height: 18px;">
<td style="text-align: center; width: 111.75px; height: 18px;">is_deleted</td>
<td style="text-align: center; width: 44.225px; height: 18px;">-</td>
<td style="text-align: center; width: 82.3625px; height: 18px;">BOOLEAN</td>
<td style="text-align: center; width: 129.25px; height: 18px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 18px;">false</td>
<td style="text-align: center; width: 156.337px; height: 18px;">Флаг удаления. True - неактивный(удален), false - активынй</td>
</tr>
<tr style="height: 18px;">
<td style="text-align: center; width: 111.75px; height: 18px;">can_read</td>
<td style="text-align: center; width: 44.225px; height: 18px;">-</td>
<td style="text-align: center; width: 82.3625px; height: 18px;">BOOLEAN</td>
<td style="text-align: center; width: 129.25px; height: 18px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 18px;">true</td>
<td style="text-align: center; width: 156.337px; height: 18px;">Разрешение на чтение догвора&nbsp;</td>
</tr>
<tr style="height: 36px;">
<td style="text-align: center; height: 36px; width: 111.75px;">can_quote</td>
<td style="text-align: center; height: 36px; width: 44.225px;">-</td>
<td style="text-align: center; height: 36px; width: 82.3625px;">BOOLEAN</td>
<td style="text-align: center; height: 36px; width: 129.25px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 36px;">true</td>
<td style="text-align: center; height: 36px; width: 156.337px;">Разрешение на пред. расчет</td>
</tr>
<tr style="height: 17px;">
<td style="text-align: center; width: 111.75px; height: 17px;">can_policy</td>
<td style="text-align: center; width: 44.225px; height: 17px;">-</td>
<td style="text-align: center; width: 82.3625px; height: 17px;">BOOLEAN</td>
<td style="text-align: center; width: 129.25px; height: 17px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 17px;">true</td>
<td style="text-align: center; width: 156.337px; height: 17px;">Разрешение на итог. расчет</td>
</tr>
<tr style="height: 18px;">
<td style="text-align: center; width: 111.75px; height: 18px;">can_addendum</td>
<td style="text-align: center; width: 44.225px; height: 18px;">-</td>
<td style="text-align: center; width: 82.3625px; height: 18px;">BOOLEAN</td>
<td style="text-align: center; width: 129.25px; height: 18px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 18px;">false</td>
<td style="text-align: center; width: 156.337px; height: 18px;">Разрешение на создание&nbsp; доп.соглашен</td>
</tr>
<tr style="height: 17px;">
<td style="text-align: center; width: 111.75px; height: 17px;">can_cancel</td>
<td style="text-align: center; width: 44.225px; height: 17px;">-</td>
<td style="text-align: center; width: 82.3625px; height: 17px;">BOOLEAN</td>
<td style="text-align: center; width: 129.25px; height: 17px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 17px;">true</td>
<td style="text-align: center; width: 156.337px; height: 17px;">Разрешение на аннулирование договора</td>
</tr>
<tr style="height: 18px;">
<td style="text-align: center; width: 111.75px; height: 18px;">can_prolongate</td>
<td style="text-align: center; width: 44.225px; height: 18px;">-</td>
<td style="text-align: center; width: 82.3625px; height: 18px;">BOOLEAN</td>
<td style="text-align: center; width: 129.25px; height: 18px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 18px;">false</td>
<td style="text-align: center; width: 156.337px; height: 18px;">Разрешение на пролонгацию договора</td>
</tr>
<tr style="height: 18px;">
<td style="text-align: center; width: 111.75px; height: 18px;">created_at</td>
<td style="text-align: center; width: 44.225px; height: 18px;">-</td>
<td style="text-align: center; width: 82.3625px; height: 18px;">TIMESTAMP</td>
<td style="text-align: center; width: 129.25px; height: 18px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 18px;">2025-11-20T15:30:00Z</td>
<td style="text-align: center; width: 156.337px; height: 18px;">Дата/время создания&nbsp;</td>
</tr>
<tr style="height: 18px;">
<td style="text-align: center; width: 111.75px; height: 18px;">updated_at</td>
<td style="text-align: center; width: 44.225px; height: 18px;">-</td>
<td style="text-align: center; width: 82.3625px; height: 18px;">TIMESTAMP</td>
<td style="text-align: center; width: 129.25px; height: 18px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 18px;">2025-11-20T15:30:00Z</td>
<td style="text-align: center; width: 156.337px; height: 18px;">Дата/время обновления&nbsp;</td>
</tr>
</tbody>
</table>
SQL для создания таблицы:
~~~
CREATE TABLE IF NOT EXISTS acc_product_roles (
    id BIGINT PRIMARY KEY ,
    tid BIGINT NOT NULL REFERENCES acc_tenants(id),
    account_id BIGINT NOT NULL REFERENCES acc_accounts(id),
    role_product_id BIGINT NOT NULL,
    role_account_id BIGINT NOT NULL REFERENCES acc_accounts(id),
    is_deleted BOOLEAN DEFAULT FALSE,
    can_read BOOLEAN DEFAULT FALSE,
    can_quote BOOLEAN DEFAULT FALSE,
    can_policy BOOLEAN DEFAULT FALSE,
    can_addendum BOOLEAN DEFAULT FALSE,
    can_cancel BOOLEAN DEFAULT FALSE,
    can_prolongate BOOLEAN DEFAULT FALSE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
~~~

## Таблица: acc_logins 
Назанчение: Список пользователей, которые могут иметь доступ к системе. Включает в себя логин, уникальный в рамках своего раздела, и обзую информацию о владельце этой учетки.
Доп. требования: настроить уникалность логина, используя для проверки user_login и tid
Структура таблицы:
<table style="height: 419px; width: 669px;">
<thead>
<tr style="height: 36px;">
<th style="text-align: center; height: 36px; width: 86.7625px;">Название поля</th>
<th style="text-align: center; height: 36px; width: 44.225px;">Ключ</th>
<th style="text-align: center; height: 36px; width: 82.3625px;">Тип поля</th>
<th style="text-align: center; height: 36px; width: 129.25px;">Обязательность</th>
<th style="text-align: center; width: 169.113px; height: 36px;">Пример</th>
<th style="text-align: center; height: 36px; width: 122.887px;">Описание</th>
</tr>
</thead>
<tbody>
<tr style="height: 36px;">
<td style="text-align: center; height: 35px; width: 86.7625px;">id</td>
<td style="text-align: center; height: 35px; width: 44.225px;">PK</td>
<td style="text-align: center; height: 35px; width: 82.3625px;">BIGINT</td>
<td style="text-align: center; height: 35px; width: 129.25px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 35px;">5553372036854775807</td>
<td style="text-align: center; height: 35px; width: 122.887px;">Идентификатор записи</td>
</tr>
<tr style="height: 36px;">
<td style="text-align: center; height: 36px; width: 86.7625px;">tid</td>
<td style="text-align: center; height: 36px; width: 44.225px;">FK</td>
<td style="text-align: center; height: 36px; width: 82.3625px;">BIGINT</td>
<td style="text-align: center; height: 36px; width: 129.25px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 36px;">9223372036854775807</td>
<td style="text-align: center; height: 36px; width: 122.887px;">Внешний ключ для связи с таблицей acc_tenants.id</td>
</tr>
<tr style="height: 18px;">
<td style="text-align: center; width: 86.7625px; height: 18px;">user_login</td>
<td style="text-align: center; width: 44.225px; height: 18px;">-</td>
<td style="text-align: center; width: 82.3625px; height: 18px;">VARCHAR(255)</td>
<td style="text-align: center; width: 129.25px; height: 18px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 18px;">user1</td>
<td style="text-align: center; width: 122.887px; height: 18px;">Логин пользователя</td>
</tr>
<tr style="height: 72px;">
<td style="text-align: center; height: 80px; width: 86.7625px;">created_at</td>
<td style="text-align: center; height: 80px; width: 44.225px;">-</td>
<td style="text-align: center; height: 80px; width: 82.3625px;">TIMESTAMP</td>
<td style="text-align: center; height: 80px; width: 129.25px;">Нет&nbsp;</td>
<td style="text-align: center; width: 169.113px; height: 80px;">2025-11-20T15:30:00Z</td>
<td style="text-align: center; height: 80px; width: 122.887px;">Дата/время создания</td>
</tr>
<tr style="height: 36px;">
<td style="text-align: center; height: 36px; width: 86.7625px;">updated_at</td>
<td style="text-align: center; height: 36px; width: 44.225px;">-</td>
<td style="text-align: center; height: 36px; width: 82.3625px;">TIMESTAMP</td>
<td style="text-align: center; height: 36px; width: 129.25px;">Нет&nbsp;</td>
<td style="text-align: center; width: 169.113px; height: 36px;">2025-11-20T15:30:00Z</td>
<td style="text-align: center; height: 36px; width: 122.887px;">Дата/время обновления</td>
</tr>
</tbody>
</table>

SQL для создания таблицы:
~~~
CREATE TABLE IF NOT EXISTS acc_logins (
    id BIGINT PRIMARY KEY ,
    tid BIGINT NOT NULL REFERENCES acc_tenants(id),
    user_login VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
    UNIQUE (user_login, tid)
);
~~~
Логика загрузки данных:
1. 

## Таблица: acc_account_logins
Назначение: Привязка пользователя к account. Пользователи и портфели имею связь много ко многим.
Так же указывается, в рамках какой интеграции (client_id), пользователь имеет доступ.
Если в токене не указано, к какому портфелю нужен доступ, то берется дефолтный портфель с isDefault = true
Такой признак можно проставить только у одного портфеля в рамках client_id
Структура таблицы
<table style="height: 295px; width: 669px;">
<thead>
<tr style="height: 36px;">
<th style="text-align: center; height: 36px; width: 80.125px;">Название поля</th>
<th style="text-align: center; height: 36px; width: 44.225px;">Ключ</th>
<th style="text-align: center; height: 36px; width: 107.488px;">Тип поля</th>
<th style="text-align: center; height: 36px; width: 129.25px;">Обязательность</th>
<th style="text-align: center; width: 169.113px; height: 36px;">Пример</th>
<th style="text-align: center; height: 36px; width: 113.975px;">Описание</th>
</tr>
</thead>
<tbody>
<tr style="height: 36px;">
<td style="text-align: center; height: 35px; width: 80.125px;">id</td>
<td style="text-align: center; height: 35px; width: 44.225px;">PK</td>
<td style="text-align: center; height: 35px; width: 107.488px;">BIGINT</td>
<td style="text-align: center; height: 35px; width: 129.25px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 35px;">5553372036854775807</td>
<td style="text-align: center; height: 35px; width: 113.975px;">Идентификатор записи</td>
</tr>
<tr style="height: 36px;">
<td style="text-align: center; height: 36px; width: 80.125px;">tid</td>
<td style="text-align: center; height: 36px; width: 44.225px;">FK</td>
<td style="text-align: center; height: 36px; width: 107.488px;">BIGINT</td>
<td style="text-align: center; height: 36px; width: 129.25px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 36px;">9223372036854775807</td>
<td style="text-align: center; height: 36px; width: 113.975px;">Внешний ключ для связи с таблицей acc_tenants.id</td>
</tr>
<tr style="height: 18px;">
<td style="text-align: center; width: 80.125px; height: 18px;">user_login</td>
<td style="text-align: center; width: 44.225px; height: 18px;">-</td>
<td style="text-align: center; width: 107.488px; height: 18px;">VARCHAR(255)</td>
<td style="text-align: center; width: 129.25px; height: 18px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 18px;">user1</td>
<td style="text-align: center; width: 113.975px; height: 18px;"></td>
</tr>
<tr style="height: 18px;">
<td style="text-align: center; width: 80.125px; height: 18px;">client_id</td>
<td style="text-align: center; width: 44.225px; height: 18px;">-</td>
<td style="text-align: center; width: 107.488px; height: 18px;">BIGINT</td>
<td style="text-align: center; width: 129.25px; height: 18px;">Нет&nbsp;</td>
<td style="text-align: center; width: 169.113px; height: 18px;"></td>
<td style="text-align: center; width: 113.975px; height: 18px;">Внешний ключ для связи с таблицей acc_clients.id&nbsp;</td>
</tr>
<tr style="height: 18px;">
<td style="text-align: center; width: 80.125px; height: 18px;">is_default</td>
<td style="text-align: center; width: 44.225px; height: 18px;">-</td>
<td style="text-align: center; width: 107.488px; height: 18px;">BOOLEAN</td>
<td style="text-align: center; width: 129.25px; height: 18px;">Нет&nbsp;</td>
<td style="text-align: center; width: 169.113px; height: 18px;"></td>
<td style="text-align: center; width: 113.975px; height: 18px;"></td>
</tr>
<tr style="height: 18px;">
<td style="text-align: center; width: 80.125px; height: 18px;">account_id</td>
<td style="text-align: center; width: 44.225px; height: 18px;">-</td>
<td style="text-align: center; width: 107.488px; height: 18px;">BIGINT</td>
<td style="text-align: center; width: 129.25px; height: 18px;">Нет&nbsp;</td>
<td style="text-align: center; width: 169.113px; height: 18px;"></td>
<td style="text-align: center; width: 113.975px; height: 18px;"></td>
</tr>
<tr style="height: 72px;">
<td style="text-align: center; height: 80px; width: 80.125px;">created_at</td>
<td style="text-align: center; height: 80px; width: 44.225px;">-</td>
<td style="text-align: center; height: 80px; width: 107.488px;">TIMESTAMP</td>
<td style="text-align: center; height: 80px; width: 129.25px;">Нет&nbsp;</td>
<td style="text-align: center; width: 169.113px; height: 80px;">2025-11-20T15:30:00Z</td>
<td style="text-align: center; height: 80px; width: 113.975px;">Дата/время создания</td>
</tr>
<tr style="height: 36px;">
<td style="text-align: center; height: 36px; width: 80.125px;">updated_at</td>
<td style="text-align: center; height: 36px; width: 44.225px;">-</td>
<td style="text-align: center; height: 36px; width: 107.488px;">TIMESTAMP</td>
<td style="text-align: center; height: 36px; width: 129.25px;">Нет&nbsp;</td>
<td style="text-align: center; width: 169.113px; height: 36px;">2025-11-20T15:30:00Z</td>
<td style="text-align: center; height: 36px; width: 113.975px;">Дата/время обновления</td>
</tr>
</tbody>
</table>

```
SQL для создания таблицы:
~~~
-- Account logins table
CREATE TABLE IF NOT EXISTS acc_account_logins (
    id BIGINT PRIMARY KEY ,
    tid BIGINT NOT NULL REFERENCES acc_tenants(id),
    user_login VARCHAR(255) NOT NULL,
    client_id BIGINT NOT NULL REFERENCES acc_clients(id),
    is_default BOOLEAN DEFAULT FALSE,
    account_id BIGINT NOT NULL REFERENCES acc_accounts(id),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (tid, user_login) REFERENCES acc_logins(tid, user_login),
    UNIQUE (user_login, account_id)
);
~~~
Логика загрузки данных:
1. 
```
## Таблица: acc_account_tokens 
Назначение таблицы: Доступ к портфелю по коду доступа. Иногда продажи проводятся на публичных сайтах, но есть потребность привязать продажи к разным портфелям.
Тогда можно сгенерить разные коды, раздать их продавцам, чтобы они вводили их при продаже и настроить этот код на определенный портфель.
Доступ только на запись. Получить данные портфеля по этому какналу не разрешено.
Сткутура таблицы 
<table style="height: 277px; width: 669px;">
<thead>
<tr style="height: 36px;">
<th style="text-align: center; height: 36px; width: 80.125px;">Название поля</th>
<th style="text-align: center; height: 36px; width: 44.225px;">Ключ</th>
<th style="text-align: center; height: 36px; width: 107.488px;">Тип поля</th>
<th style="text-align: center; height: 36px; width: 129.25px;">Обязательность</th>
<th style="text-align: center; width: 169.113px; height: 36px;">Пример</th>
<th style="text-align: center; height: 36px; width: 113.975px;">Описание</th>
</tr>
</thead>
<tbody>
<tr style="height: 36px;">
<td style="text-align: center; height: 35px; width: 80.125px;">id</td>
<td style="text-align: center; height: 35px; width: 44.225px;">PK</td>
<td style="text-align: center; height: 35px; width: 107.488px;">BIGINT</td>
<td style="text-align: center; height: 35px; width: 129.25px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 35px;">5553372036854775807</td>
<td style="text-align: center; height: 35px; width: 113.975px;">Идентификатор записи</td>
</tr>
<tr style="height: 36px;">
<td style="text-align: center; height: 36px; width: 80.125px;">tid</td>
<td style="text-align: center; height: 36px; width: 44.225px;">FK</td>
<td style="text-align: center; height: 36px; width: 107.488px;">BIGINT</td>
<td style="text-align: center; height: 36px; width: 129.25px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 36px;">9223372036854775807</td>
<td style="text-align: center; height: 36px; width: 113.975px;">Внешний ключ для связи с таблицей acc_tenants.id</td>
</tr>
<tr style="height: 18px;">
<td style="text-align: center; width: 80.125px; height: 18px;">token</td>
<td style="text-align: center; width: 44.225px; height: 18px;">-</td>
<td style="text-align: center; width: 107.488px; height: 18px;">VARCHAR(255)</td>
<td style="text-align: center; width: 129.25px; height: 18px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 18px;"></td>
<td style="text-align: center; width: 113.975px; height: 18px;"></td>
</tr>
<tr style="height: 18px;">
<td style="text-align: center; width: 80.125px; height: 18px;">client_id</td>
<td style="text-align: center; width: 44.225px; height: 18px;">-</td>
<td style="text-align: center; width: 107.488px; height: 18px;">BIGINT</td>
<td style="text-align: center; width: 129.25px; height: 18px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 18px;"></td>
<td style="text-align: center; width: 113.975px; height: 18px;"></td>
</tr>
<tr style="height: 18px;">
<td style="text-align: center; width: 80.125px; height: 18px;">account_id</td>
<td style="text-align: center; width: 44.225px; height: 18px;">-</td>
<td style="text-align: center; width: 107.488px; height: 18px;">BIGINT</td>
<td style="text-align: center; width: 129.25px; height: 18px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 18px;"></td>
<td style="text-align: center; width: 113.975px; height: 18px;"></td>
</tr>
<tr style="height: 72px;">
<td style="text-align: center; height: 80px; width: 80.125px;">created_at</td>
<td style="text-align: center; height: 80px; width: 44.225px;">-</td>
<td style="text-align: center; height: 80px; width: 107.488px;">TIMESTAMP</td>
<td style="text-align: center; height: 80px; width: 129.25px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 80px;">2025-11-20T15:30:00Z</td>
<td style="text-align: center; height: 80px; width: 113.975px;">Дата/время создания</td>
</tr>
<tr style="height: 36px;">
<td style="text-align: center; height: 36px; width: 80.125px;">updated_at</td>
<td style="text-align: center; height: 36px; width: 44.225px;">-</td>
<td style="text-align: center; height: 36px; width: 107.488px;">TIMESTAMP</td>
<td style="text-align: center; height: 36px; width: 129.25px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 36px;">2025-11-20T15:30:00Z</td>
<td style="text-align: center; height: 36px; width: 113.975px;">Дата/время обновления</td>
</tr>
</tbody>
</table>
SQL для создания таблицы:
```
~~~
-- Account tokens table
CREATE TABLE IF NOT EXISTS acc_account_tokens (
    id BIGINT PRIMARY KEY,
    tid BIGINT NOT NULL REFERENCES acc_tenants(id),
    token VARCHAR(255) NOT NULL,
    client_id BIGINT NOT NULL REFERENCES acc_clients(id),
    account_id BIGINT NOT NULL REFERENCES acc_accounts(id),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    UNIQUE (token, client_id)
);
~~~
```
Логика загрузки данных:
1. 
