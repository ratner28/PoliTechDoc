### Добавить тенанта 
Шаг 1. 
##### Вводная
В контексте проекта тенант (tenant,арендатор) — это логически изолированное пространство внутри приложения. Представьте это как отдельную "виртуальную" копию программы для конкретного клиента или организации. Для хранения списка этих изолированных пространств (арендаторов) будет использоваться таблица acc_tenants.
##### Описание шага:
Мы начинаем работу с создания тенанта под  названием "VSK" в таблице acc_tenants. Тенант "VSK" -  наш первый и главный арендатор в системе.
Он обеспечивает логическую изоляцию данных для всех учетных записей (аккаунтов), которые будут созданы на начальном этапе работы приложения.
тенант  создается один раз при инициализации таблицы. Для того, чтобы создать тенант а выполнить след. действия:

Выполнить прямой SQL-запрос INSERT в таблицу acc_tenants
```
INSERT INTO acc_tenants (id, code, name, is_deleted, created_at)
VALUES ('1', 'VSK', 'Вск. Продажа договоров страхования' 'false', '2025-11-20T15:30:00Z');
```
ИЛИ 
Использовать метод POST /tnts, где на вход передать значение code = VSK И name = ВСК (см. описание метода <a href="https://github.com/AsyaBarinova/PoliTechDoc/blob/patch-1/auth/acc_tenants.md">https://github.com/AsyaBarinova/PoliTechDoc/blob/patch-1/auth/acc_tenants.md</a>&nbsp;)

<p>Результат шага: создан тенант </p>
<p>Пример записи в таблице:</p> 
<table border="1" style="border-collapse: collapse; width: 100%; height: 72px;">
<tbody>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;">id</td>
<td style="width: 25%; height: 18px;">code</td>
<td style="width: 25%; height: 18px;">name</td> 
<td style="width: 25%; height: 18px;">is_deleted</td>
<td style="width: 12.5%; height: 18px;">created_at</td>
<td style="width: 12.5%;">updated_at</td>
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;">1</td>
<td style="width: 25%; height: 18px;">VSK</td>
<td style="width: 25%; height: 18px;">Вск. Продажа договоров страхования</td> 
<td style="width: 25%; height: 18px;">false</td>
<td style="width: 12.5%; height: 18px;">2025-11-20T15:30:00Z</td>
<td style="width: 12.5%;">NULL</td>
</tr>
</tbody>
</table>
<p></p>
<p></p>

##### Комментарий
<p>На данный момент архитектура приложения предполагает, что абсолютно все будущие аккаунты пользователей будут привязаны к одному-единственному тенанту "VSK".
В будущем, если потребуется поддерживать другю модель, то мы сможем добавлять новых тенантов в эту таблицу. Пока же все работают в рамках одного пространства "VSK".</p>

### Добавить клиента(партнера)
Шаг 2.
##### Вводная
Клиент (партнер) — это внешний контрагент (организация или сервис), который использует функционал нашего приложения. Для хранения информации о партнерских подключениях к тенантам будем использовать таблицу acc_clients. 

##### Описание шага:
Для создания нового Партнера и привязке его к конкретному Тенанту VSK, необходимо добавить соответствующую запись в таблицу acc_clients.
В качестве примера мы создадим партнера под названием "СРАВНИ". Добавление записи можно осуществить следующими способами:

Выполнить прямой SQL-запрос INSERT в таблицу acc_clients
```
INSERT INTO acc_clients (id, tid, client_id, name, is_deleted, created_at )
VALUES ('2', '1', 'СРАВНИ', 'SRAVNI', 'false', '2025-11-20T15:30:00Z');
```
ИЛИ 

Использовать метод POST /tnts/{tenantId}/clients (см. описание метода https://github.com/AsyaBarinova/PoliTechDoc/blob/patch-1/auth/acc_clients.md)
<p>Результат шага: создан партнер, привязанный к определенному тенант у VSK</p>
<p>Пример записи в таблице:</p> 
<table border="1" style="border-collapse: collapse; width: 100%; height: 72px;">
<tbody>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;">id</td>
  <td style="width: 25%; height: 18px;">tid</td>
<td style="width: 25%; height: 18px;">client_id</td>  
<td style="width: 25%; height: 18px;">default_account_id</td>
  <td style="width: 12.5%; height: 18px;">name</td>
<td style="width: 12.5%;">is_deleted</td>
<td style="width: 12.5%;">created_at</td>  
<td style="width: 12.5%;">updated_at</td>    
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;">2</td>
<td style="width: 25%; height: 18px;">1</td>
<td style="width: 25%; height: 18px;">SRAVNI</td>
<td style="width: 12.5%; height: 18px;">NULL</td>
<td style="width: 12.5%;">СРАВНИ</td>
<td style="width: 12.5%;">false</td>  
<td style="width: 12.5%;">2025-11-20T15:30:00Z</td>  
<td style="width: 12.5%;">NULL</td>    
</tr>
</tbody>
</table>
<p></p>
<p></p>

### Добавить аккаунт 
Шаг 3.
##### Вводная
<p>Аккаунт (аccount) &mdash; это "виртуальный субъект", от имени которого работают пользователи. К одному account может быть привязано несколько логинов (учётных записей людей).</p>
<p>Это даёт следующие преимущества:</p>
<ul>
<li>несколько сотрудников могут работать с одним и тем же портфелем (например, отдел корпоративных продаж);</li>
<li>один пользователь может иметь доступ к нескольким account (например, агент ведёт несколько страховых портфелей);</li>
<li>при смене сотрудников нет необходимости изменять сам account &mdash; достаточно переназначить привязку логинов.</li>
</ul>
<p dir="auto">У каждого account определяется набор ролей и прав, который определяет:</p>
<ul>
<li dir="auto">какие действия доступны (создание договора, чтение договора и др.);</li>
<li dir="auto">какие продукты можно продовать</li>
</ul>
<p dir="auto">Таким образом, права назначаются на account, а пользователи наследуют эти права через привязку к нему.</p>
<p dir="auto">Account встроен в иерархию компании:</p>
<ul>
<li dir="auto">на верхнем уровне могут быть глобальные account (например, маркетплейс в целом);</li>
<li dir="auto">ниже &mdash; account брокеров или филиалов;</li>
<li dir="auto">ещё ниже &mdash; account отдельных портфелей или команд.</li>
</ul>
<div class="markdown-heading" dir="auto"></div>
<p dir="auto">В страховании account также можно рассматривать как портфель:</p>
<ul>
<li dir="auto">в него входят договоры, клиенты, продукты;</li>
<li dir="auto">к нему привязаны пользователи (агенты, менеджеры);</li>
<li dir="auto">на уровне account настраиваются комиссии, лимиты и права</li>
</ul>
Для хранения списка аакунтов будет использоваться таблица acc_accounts

##### Описание шага:

### Добавить пользователя (УЗ)
##### Вводная
<p>Учетная запись пользователя содержит следующие данные: логин (электронная почта), пароль, ФИО и должность пользователя, имеющего доступ в систему.</p>
<p>УЗ заводятся в рамках тенанта. При этом одна УЗ может быть привязана к нескольким разным портфелям (account), связь обеспечивает таблица acc_accounts_logins. Для хранения информации об учетных записях используется таблица acc_logins.</p>

##### Описание шага:
###### Создание УЗ
Для создания новой УЗ и привязки тенанту, необходимо добавить соответствующую запись в таблицу acc_logins следующими способами:

Выполнить прямой SQL-запрос INSERT в таблицу acc_logins
```
INSERT INTO acc_logins (id, tid, user_login, full_name, position, is_deleted, created_at)
VALUES ('2', '1', 'olga.p1@gmail.com', 'Пивоварова Ольга Васильевна', 'Страховой агент', 'false', '2025-11-20T15:30:00Z');
```
ИЛИ 

Использовать метод POST /tnts/{tenantId}/logins (см. описание метода https://github.com/ratner28/PoliTechDoc/blob/patch-2/auth/acc_logins.md)

<p>Пример записи в таблице:</p> 
<table border="1" style="border-collapse: collapse; width: 100%; height: 72px;">
<tbody>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;">id</td>
<td style="width: 25%; height: 18px;">tid</td>
<td style="width: 25%; height: 18px;">user_login</td>
<td style="width: 25%; height: 18px;">password</td>
<td style="width: 25%; height: 18px;">full_name</td>
<td style="width: 12.5%; height: 18px;">position</td>
<td style="width: 12.5%;">is_deleted</td>
<td style="width: 12.5%;">created_at</td>  
<td style="width: 12.5%;">updated_at</td>    
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;">2</td>
<td style="width: 25%; height: 18px;">1</td>
<td style="width: 25%; height: 18px;">olga.p1@gmail.com</td>
<td style="width: 12.5%; height: 18px;">null</td>
<td style="width: 12.5%; height: 18px;">Пивоварова Ольга Васильевна</td>
<td style="width: 12.5%;">Страховой агент</td>
<td style="width: 12.5%;">false</td>  
<td style="width: 12.5%;">2025-11-20T15:30:00Z</td>  
<td style="width: 12.5%;">NULL</td>    
</tr>
</tbody>
</table>
<p></p>
<p></p>

###### Добавление (изменение) пароля для УЗ
Для добавления пароля для УЗ необходимо использовать метод POST /api/auth/set-password (см. описание метода https://github.com/ratner28/PoliTechDoc/blob/patch-2/auth/acc_logins.md). Чтобы создать/поменять пароль у пользователя должна быть назначена роль SYS_ADMIN.
После вызова метода пароль хешируется, и его хеш-сумма сохраняется в таблице.

<p>Пример записи в таблице:</p> 
<table border="1" style="border-collapse: collapse; width: 100%; height: 72px;">
<tbody>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;">id</td>
<td style="width: 25%; height: 18px;">tid</td>
<td style="width: 25%; height: 18px;">user_login</td>
<td style="width: 25%; height: 18px;">password</td>
<td style="width: 25%; height: 18px;">full_name</td>
<td style="width: 12.5%; height: 18px;">position</td>
<td style="width: 12.5%;">is_deleted</td>
<td style="width: 12.5%;">created_at</td>  
<td style="width: 12.5%;">updated_at</td>    
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;">2</td>
<td style="width: 25%; height: 18px;">1</td>
<td style="width: 25%; height: 18px;">olga.p1@gmail.com</td>
<td style="width: 12.5%; height: 18px;">3fd90706aa13b38f74ba8e0ca16cd598</td>
<td style="width: 12.5%; height: 18px;">Пивоварова Ольга Васильевна</td>
<td style="width: 12.5%;">Страховой агент</td>
<td style="width: 12.5%;">false</td>  
<td style="width: 12.5%;">2025-11-20T15:30:00Z</td>  
<td style="width: 12.5%;">2025-11-21T15:30:00Z</td>    
</tr>
</tbody>
</table>
<p></p>
<p></p>
