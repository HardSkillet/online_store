<h1>Описание</h1>

Сайт - онлайн магазин.

Позволяет просматривать страницы с девайсами разного типа и различных брендов. Зарегистрированным в системе пользователям позволяет добавлять девайсы в корзину и оценивать товар. Администраторы могут добавлять новые бренды, типы товара и девайсы, а так же производить их удаление, просматривать очереди с заказами.


<h1>Наименование базы данных</h1>

online_store

<h1>Предметная область</h1>

Онлайн магазин. Электроника. Покупка товаров.

<h1>Данные</h1>

<strong>User</strong>
<table border="1">
<tr bgcolor="#CCCCCC">
<td align="center"><strong>Name</strong></td>
<td align="center"><strong>Type</strong></td>
<td align="center"><strong>Constrains</strong></td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">id</td>
<td align="center">INTEGER</td>
<td align="center">PRIMARY KEY AUTO INCREMENT NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">email</td>
<td align="center">string</td>
<td align="center">UNIQUE NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">password</td>
<td align="center">STRING</td>
<td align="center">NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">role</td>
<td align="center">STRING</td>
<td align="center">DEFAULT VALUE: "USER"</td>
</tr>
</table>

<strong>Basket</strong>
<table border="1">
<tr bgcolor="#CCCCCC">
<td align="center"><strong>Name</strong></td>
<td align="center"><strong>Type</strong></td>
<td align="center"><strong>Constrains</strong></td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">id</td>
<td align="center">INTEGER</td>
<td align="center">PRIMARY KEY AUTO INCREMENT NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">user_id</td>
<td align="center">INTEGER</td>
<td align="center">FOREIGN KEY NOT NULL</td>
</tr>
</table>

<strong>Device</strong>
<table border="1">
<tr bgcolor="#CCCCCC">
<td align="center"><strong>Name</strong></td>
<td align="center"><strong>Type</strong></td>
<td align="center"><strong>Constrains</strong></td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">id</td>
<td align="center">INTEGER</td>
<td align="center">PRIMARY KEY AUTO INCREMENT NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">name</td>
<td align="center">STRING</td>
<td align="center">UNIQUE NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">price</td>
<td align="center">INTEGER</td>
<td align="center">NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">rating</td>
<td align="center">INTEGER</td>
<td align="center">DEFAULT VALUE: 0</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">img</td>
<td align="center">STRING</td>
<td align="center">NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">type_id</td>
<td align="center">INTEGER</td>
<td align="center">FOREIGN KEY NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">brand_id</td>
<td align="center">INTEGER</td>
<td align="center">FOREIGN KEY NOT NULL</td>
</tr>
</table>

<strong>Type</strong>
<table border="1">
<tr bgcolor="#CCCCCC">
<td align="center"><strong>Name</strong></td>
<td align="center"><strong>Type</strong></td>
<td align="center"><strong>Constrains</strong></td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">id</td>
<td align="center">INTEGER</td>
<td align="center">PRIMARY KEY AUTO INCREMENT NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">device_id</td>
<td align="center">INTEGER</td>
<td align="center">FOREIGN KEY NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">name</td>
<td align="center">STRING</td>
<td align="center">UNIQUE NOT NULL</td>
</table>

<strong>Brand</strong>
<table border="1">
<tr bgcolor="#CCCCCC">
<td align="center"><strong>Name</strong></td>
<td align="center"><strong>Type</strong></td>
<td align="center"><strong>Constrains</strong></td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">id</td>
<td align="center">INTEGER</td>
<td align="center">PRIMARY KEY AUTO INCREMENT NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">device_id</td>
<td align="center">INTEGER</td>
<td align="center">FOREIGN KEY NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">name</td>
<td align="center">STRING</td>
<td align="center">UNIQUE NOT NULL</td>
</table>

<strong>Rating</strong>
<table border="1">
<tr bgcolor="#CCCCCC">
<td align="center"><strong>Name</strong></td>
<td align="center"><strong>Type</strong></td>
<td align="center"><strong>Constrains</strong></td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">id</td>
<td align="center">INTEGER</td>
<td align="center">PRIMARY KEY AUTO INCREMENT NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">device_id</td>
<td align="center">INTEGER</td>
<td align="center">FOREIGN KEY NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">user_id</td>
<td align="center">INTEGER</td>
<td align="center">FOREIGN KEY NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">rate</td>
<td align="center">INTEGER</td>
<td align="center">NOT NULL</td>
</table>

<strong>Device_info</strong>
<table border="1">
<tr bgcolor="#CCCCCC">
<td align="center"><strong>Name</strong></td>
<td align="center"><strong>Type</strong></td>
<td align="center"><strong>Constrains</strong></td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">id</td>
<td align="center">INTEGER</td>
<td align="center">PRIMARY KEY AUTO INCREMENT NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">device_id</td>
<td align="center">INTEGER</td>
<td align="center">FOREIGN KEY NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">title</td>
<td align="center">STRING</td>
<td align="center">NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">description</td>
<td align="center">STRING</td>
<td align="center">NOT NULL</td>
</table>

<strong>TypeBrand</strong>
<table border="1">
<tr bgcolor="#CCCCCC">
<td align="center"><strong>Name</strong></td>
<td align="center"><strong>Type</strong></td>
<td align="center"><strong>Constrains</strong></td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">type_id</td>
<td align="center">INTEGER</td>
<td align="center">FOREIGN KEY NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">brand_id</td>
<td align="center">INTEGER</td>
<td align="center">FOREIGN KEY NOT NULL</td>
</tr>
</table>

<strong>Orders</strong>
<table border="1">
<tr bgcolor="#CCCCCC">
<td align="center"><strong>Name</strong></td>
<td align="center"><strong>Type</strong></td>
<td align="center"><strong>Constrains</strong></td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">id</td>
<td align="center">INTEGER</td>
<td align="center">PRIMARY KEY AUTO INCREMENT NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">complete</td>
<td align="center">BIT</td>
<td align="center">DEFAULT VALUE: false</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">user_id</td>
<td align="center">INTEGER</td>
<td align="center">FOREIGN KEY NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">mobile</td>
<td align="center">STRING</td>
<td align="center">NOT NULL</td>
</tr>
</table>

<strong>OrderDevice</strong>
<table border="1">
<tr bgcolor="#CCCCCC">
<td align="center"><strong>Name</strong></td>
<td align="center"><strong>Type</strong></td>
<td align="center"><strong>Constrains</strong></td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">id</td>
<td align="center">INTEGER</td>
<td align="center">PRIMARY KEY AUTO INCREMENT NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">device_id</td>
<td align="center">INTEGER</td>
<td align="center">FOREIGN KEY NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">order_id</td>
<td align="center">INTEGER</td>
<td align="center">FOREIGN KEY NOT NULL</td>
</tr>
<tr bgcolor="#CCCCCC">
<td align="center">count</td>
<td align="center">INTEGER</td>
<td align="center">NOT NULL</td>
</tr>
</table> 

<h2>Общие ограничения целостности</h2>

Связь one to many: user и rating, orders и orders_device, type и device, brand и device, device и device_info, device и rating.

Связь one to one: user и basket, basket_device и device.

Связь zero or one to many: user и orders.

<h1>Пользовательские роли</h1>

<h2>Неавторизованный пользователь(количество не ограничено)</h2>

Просмотр страницы с девайсами, сортировка по брендам и типам

<h2>Авторизованный пользователь (количество не ограничено)</h2>

Просмотр страницы с девайсами, сортировка по брендам и типам. Возможность добавления товаров в корзину и выставления товару рейтинга.

<h2>Администраторы (количество не ограничено)</h2>

Возможности авторизованного пользователя + добавление/удаление девайсов/брендов/типов + просмотр страницы с заказами пользователей.
