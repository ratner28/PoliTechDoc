### Добавить тената 
Шаг 1. 
##### Вводная
В контексте проекта тенант (tenant,арендатор) — это логически изолированное пространство внутри приложения. Представьте это как отдельную "виртуальную" копию программы для конкретного клиента или организации. Для хранения списка этих изолированных пространств (арендаторов) будет использоваться таблица acc_tenants.
##### Описание шага:
Мы начинаем работу с создания тенанта под  названием "VSK" в таблице acc_tenants. Тенант "VSK" -  наш первый и главный арендатор в системе.
Он обеспечивает логическую изоляцию данных для всех учетных записей (аккаунтов), которые будут созданы на начальном этапе работы приложения.
Тенат создается один раз при инициализации таблицы. Для того, чтобы создать тената выполнить след. действия:
1. Выполнить INSERT в таблицу acc_tenants
```
INSERT INTO acc_tenants (id, code, name, is_deleted, created_at)
VALUES ('1', 'VSK', 'Вск. Продажа договоров страхования' 'false', '2025-11-20T15:30:00Z');
```
ИЛИ 
1. Использовать метод POST /tnts, где на вход передать значение code = VSK (см. описание метода <a href="https://github.com/AsyaBarinova/PoliTechDoc/blob/patch-1/auth/acc_clients.md">PoliTechDoc/auth/acc_clients.md at patch-1 &middot; AsyaBarinova/PoliTechDoc</a>)

<p>Результат шага: создан тенат</p>
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
