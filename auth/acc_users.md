## Таблица: acc_users
#### Назначение таблицы: Хранение информации о пользователях
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
<tr style="height: 44px;">
<td style="text-align: center; width: 133.712px; height: 43px;">id</td>
<td style="text-align: center; width: 44.225px; height: 43px;">PK</td>
<td style="text-align: center; width: 107.488px; height: 43px;">BIGINT</td>
<td style="text-align: center; width: 129.25px; height: 43px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 43px;"><span>2</span></td>
<td style="text-align: center; width: 157.55px; height: 43px;">ИД пользователя</td>
</tr>
<tr style="height: 36px;">
<td style="text-align: center; width: 133.712px; height: 36px;">tid</td>
<td style="text-align: center; width: 44.225px; height: 36px;">FK</td>
<td style="text-align: center; width: 107.488px; height: 36px;">BIGINT</td>
<td style="text-align: center; width: 129.25px; height: 36px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 36px;"><span>1</span></td>
<td style="text-align: center; width: 157.55px; height: 36px;">Внешний ключ для связи с таблицей&nbsp;acc_tenants</td>
</tr>
<tr style="height: 36px;">
<td style="text-align: center; width: 133.712px; height: 36px;">user_login</td>
<td style="text-align: center; width: 44.225px; height: 36px;">-</td>
<td style="text-align: center; width: 107.488px; height: 36px;">VARCHAR(250)</td>
<td style="text-align: center; width: 129.25px; height: 36px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 36px;"><span>ratner@vsk.ru</span></td>
<td style="text-align: center; width: 157.55px; height: 36px;">Логин пользователя</td>
</tr>
<tr style="height: 36px;">
<td style="text-align: center; width: 133.712px; height: 36px;">full_name</td>
<td style="text-align: center; width: 44.225px; height: 36px;">-</td>
<td style="text-align: center; width: 107.488px; height: 36px;">VARCHAR(250)</td>
<td style="text-align: center; width: 129.25px; height: 36px;">Да</td>
<td style="text-align: center; width: 169.113px; height: 36px;">Ратнер Екатерина Александровна</td>
<td style="text-align: center; width: 157.55px; height: 36px;">ФИО</td>
</tr>
<tr style="height: 36px;">
<td style="text-align: center; width: 133.712px; height: 36px;">job_title</td>
<td style="text-align: center; width: 44.225px; height: 36px;">-</td>
<td style="text-align: center; width: 107.488px; height: 36px;">VARCHAR(250)</td>
<td style="text-align: center; width: 129.25px; height: 36px;">Нет</td>
<td style="text-align: center; width: 169.113px; height: 36px;">Страховой агент</td>
<td style="text-align: center; width: 157.55px; height: 36px;">Должность</td>
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
CREATE TABLE IF NOT EXISTS acc_users (
    id BIGINT PRIMARY KEY ,
    tid BIGINT NOT NULL REFERENCES acc_tenants(id),
    user_login VARCHAR(255) NOT NULL,
    full_name VARCHAR(255) NOT NULL,
    job_title VARCHAR(255),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
    UNIQUE (user_login, tid)
);
~~~
### Логика загрузки данных
#### Название метода: 
```
POST /tnts/{tenantCode}/users
```
#### Назначние метода: Создание пользователя
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
<td style="width: 25%; height: 18px;"><span>userLogin</span></td>
<td style="width: 12.5%; height: 18px;"><span>string</span></td>
<td style="width: 12.5%; text-align: center; height: 18px;"><span>Да</span></td>
<td style="width: 50%; height: 18px;"><span>Логин пользователя</span></td>
</tr>
<tr style="height: 90px;">
<td style="width: 25%; height: 90px;"><span>fullName</span></td>
<td style="width: 12.5%; height: 90px;"><span>string</span></td>
<td style="width: 12.5%; text-align: center; height: 90px;"><span>Да</span></td>
<td style="width: 50%; height: 90px;"><span>ФИО пользователя</span></td>
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;"><span>jobTitle</span></td>
<td style="width: 12.5%; height: 18px;"><span>string</span></td>
<td style="width: 12.5%; text-align: center; height: 18px;"><span>Нет</span></td>
<td style="width: 50%; height: 18px;"><span>Должность</span></td>
</tr>
</tbody>
</table>
<p>Пример запроса:&nbsp;</p>
<pre> {
 "userLogin": "ratner@vsk.ru", 
 "fullName": "Ратнер Екатерина Александровна", 
 "jobTitle": "Страховой агент"
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
<td style="width: 50%; height: 18px;"><span>&nbsp;ИД пользователя</span></td>
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;"><span>userLogin</span></td>
<td style="width: 12.5%; height: 18px;"><span>string</span></td>
<td style="width: 12.5%; text-align: center; height: 18px;"><span>Да</span></td>
<td style="width: 50%; height: 18px;"><span>Логин пользователя</span></td>
</tr>
<tr style="height: 90px;">
<td style="width: 25%; height: 90px;"><span>fullName</span></td>
<td style="width: 12.5%; height: 90px;"><span>&nbsp;string</span></td>
<td style="width: 12.5%; text-align: center; height: 90px;"><span>Да</span></td>
<td style="width: 50%; height: 90px;"><span>ФИО пользователя</span></td>
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;"><span>jobTitle</span></td>
<td style="width: 12.5%; height: 18px;"><span>string</span></td>
<td style="width: 12.5%; text-align: center; height: 18px;"><span>Нет</span></td>
<td style="width: 50%; height: 18px;"><span>Должность</span></td>
</tr>
</tbody>
</table>
<p></p>
<p>Пример ответа:&nbsp;</p>
<p>Успех, код ответа 201</p>
<pre> {
 "id": "5544888",
 "userLogin": "ratner@vsk.ru", 
 "fullName": "Ратнер Екатерина Александровна",
 "jobTitle": "Страховой агент" 
  }
</pre>
