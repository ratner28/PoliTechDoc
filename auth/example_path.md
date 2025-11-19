### Добавить тената 
Шаг 1. 
##### Вводная
В контексте проекта тенант (tenant,арендатор) — это логически изолированное пространство внутри приложения. Представьте это как отдельную "виртуальную" копию программы для конкретного клиента или организации. Для хранения списка этих изолированных пространств (арендаторов) будет использоваться таблица acc_tenants.
##### Описание шага:
Мы начинаем работу с создания тенанта под  названием "VSK" в таблице acc_tenants. Тенант "VSK" -  наш первый и главный арендатор в системе.
Он обеспечивает логическую изоляцию данных для всех учетных записей (аккаунтов), которые будут созданы на начальном этапе работы приложения.
Тенат создается один раз при инициализации таблицы. Для того, чтобы создать тената выполнить след. действия:
1. Выполнить INSERT в таблицу acc_clients
```
INSERT INTO acc_tenants (id, name, is_deleted, created_at)
VALUES ('1', 'VSK', 'false', '2025-11-20T15:30:00Z');
```
ИЛИ 
1. Использовать метод /tnts, где на вход передать значение name = VSK (см. описание метода <a href="https://github.com/AsyaBarinova/PoliTechDoc/blob/patch-1/auth/acc_clients.md">PoliTechDoc/auth/acc_clients.md at patch-1 &middot; AsyaBarinova/PoliTechDoc</a>)

Результат шага: создан тенат
Пример записи в таблице: 
<table border="1" style="border-collapse: collapse; width: 100%; height: 72px;">
<tbody>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;">id</td>
<td style="width: 25%; height: 18px;">name</td>
<td style="width: 25%; height: 18px;">is_deleted</td>
<td style="width: 12.5%; height: 18px;">created_at</td>
<td style="width: 12.5%;">updated_at</td>
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;">1</td>
<td style="width: 25%; height: 18px;">VSK</td>
<td style="width: 25%; height: 18px;">false</td>
<td style="width: 12.5%; height: 18px;">2025-11-20T15:30:00Z</td>
<td style="width: 12.5%;">NULL</td>
</tr>
</tbody>
</table>
<p></p>
<p></p>

##### Комментарий
На данный момент архитектура приложения предполагает, что абсолютно все будущие аккаунты пользователей будут привязаны к одному-единственному тенанту "VSK".
В будущем, если потребуется поддерживать другю модель, то мы сможем добавлять новых тенантов в эту таблицу. Пока же все работают в рамках одного пространства "VSK".

Шаг 2. Создаем партнера (клиента) в таблице acc_clients
<table border="1" style="border-collapse: collapse; width: 100%; height: 72px;">
<tbody>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;">tid</td>
<td style="width: 25%; height: 18px;">id</td>
<td style="width: 25%; height: 18px;">client_id</td>  
<td style="width: 25%; height: 18px;">default_account_id</td>
<td style="width: 12.5%; height: 18px;">name</td>
<td style="width: 12.5%;">is_deleted</td>
<td style="width: 12.5%;">created_at</td>  
<td style="width: 12.5%;">updated_at</td>    
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;">1111111111111111</td>
<td style="width: 25%; height: 18px;">2222222222222222</td>
<td style="width: 25%; height: 18px;">SRAVNI</td>
<td style="width: 12.5%; height: 18px;">?</td>
<td style="width: 12.5%;">Сравни.ру</td>
<td style="width: 12.5%;">false</td>  
<td style="width: 12.5%;">2025-11-20T15:30:00Z</td>  
<td style="width: 12.5%;">NULL</td>    
</tr>
</tbody>
</table>
<p></p>
<p></p>
Шаг 3. Создаем  аккаунт для партнера Сравни.ру в таблице acc_accounts 
<p>Аккаунт (account)  — это "виртуальный субъект", от имени которого работают пользователи.</p>
<table border="1" style="border-collapse: collapse; width: 100%; height: 72px;">
<tbody>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;">id</td>
<td style="width: 25%; height: 18px;">tid</td>
<td style="width: 25%; height: 18px;">client_id</td>  
<td style="width: 25%; height: 18px;">parent_id</td>
<td style="width: 12.5%; height: 18px;">node_type</td>
<td style="width: 12.5%;">name</td>
<td style="width: 12.5%;">created_at</td>  
<td style="width: 12.5%;">updated_at</td>    
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;">3333333333333</td>
<td style="width: 25%; height: 18px;">2222222222222222</td>
<td style="width: 25%; height: 18px;">1111111111111111</td>  
<td style="width: 25%; height: 18px;">?</td>
<td style="width: 12.5%; height: 18px;">ACCOUNT</td>
<td style="width: 12.5%;">Сравни.ру</td>
<td style="width: 12.5%;">2025-11-20T15:30:00Z</td>  
<td style="width: 12.5%;">NULL</td>    
</tr>
</tbody>
</table>
Шаг 4. Подключаем продукт для аккаунта Сравни.ру в таблице acc_product_roles 

<table border="1" style="border-collapse: collapse; width: 100%; height: 72px;">
<tbody>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;">id</td>
<td style="width: 25%; height: 18px;">tid</td>
<td style="width: 25%; height: 18px;">account_id</td>  
<td style="width: 25%; height: 18px;">role_product_id</td>
<td style="width: 12.5%; height: 18px;">role_account_id</td>
<td style="width: 12.5%;">is_deleted</td>
<td style="width: 12.5%;">can_read</td>  
<td style="width: 12.5%;">can_quote</td>    
<td style="width: 12.5%;">can_policy</td> 
<td style="width: 12.5%;">can_addendum</td> 
<td style="width: 12.5%;">can_cancel</td> 
<td style="width: 12.5%;">can_prolongate</td> 
<td style="width: 12.5%;">created_at</td> 
<td style="width: 12.5%;">updated_at</td> 
</tr>
<tr style="height: 18px;">
<td style="width: 25%; height: 18px;">4444444444</td>
<td style="width: 25%; height: 18px;">2222222222222222</td>
<td style="width: 25%; height: 18px;">3333333333333</td>  
<td style="width: 25%; height: 18px;">role_product_id</td>
<td style="width: 12.5%; height: 18px;">?</td>
<td style="width: 12.5%;">false</td>
<td style="width: 12.5%;">true</td>  
<td style="width: 12.5%;">true</td>    
<td style="width: 12.5%;">true</td> 
<td style="width: 12.5%;">false</td> 
<td style="width: 12.5%;">true</td> 
<td style="width: 12.5%;">true</td> 
<td style="width: 12.5%;">2025-11-20T15:30:00Z</td> 
<td style="width: 12.5%;">NULL</td> 
</tr>   
</tbody>
</table>
