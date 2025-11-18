Шаг 1.Создаем тената PARTAPI в таблице acc_tenants
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
<td style="width: 25%; height: 18px;">1111111111111111</td>
<td style="width: 25%; height: 18px;">PARTAPI</td>
<td style="width: 25%; height: 18px;">false</td>
<td style="width: 12.5%; height: 18px;">2025-11-20T15:30:00Z</td>
<td style="width: 12.5%;">NULL</td>
</tr>
</tbody>
</table>
<p></p>
<p></p>

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
