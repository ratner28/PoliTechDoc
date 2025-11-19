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
<td style="text-align: center; width: 169.113px; height: 36px;"><span>5553372036854775807</span></td>
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
<p>Идентифкатор тената</p>
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
<td style="width: 25%; height: 90px;"><span>default_account_id</span></td>
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
 "default_account_id": "3"
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
<td style="width: 25%; height: 90px;"><span>default_account_id</span></td>
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
<p></p>
<p>Пример ответа:&nbsp;</p>
<p>Успех, код ответа 200</p>
<pre> {
 "id": "2",
 "default_account_id": "3",
 "clientId": "SRAVNI", 
 "name": "СРАВНИ" 
  }
</pre>
