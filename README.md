# Использование 

1. Подключаем класс

	```php
	require('VimeWorldAPI.class.php');
	```

2. Создаем объект

	1. Без токена
	```php
	$api = new VimeWorldAPI();
	```
	2. С токеном 
	```php
	$api = new VimeWorldAPI('token');
	```
	
3. Используем API

	1. Вывод информации о игроке
		1. По никнейму
			1. Один игрок
				```php
				$api->user('LoganFrench');
				```
			2. Несколько игроков
				```php
				$api->user([ 'LoganFrench', 'xtrafrancyz' ]);
				```
		2. По ID
			1. Один игрок
				```php
				$api->user(1249617);
				```
			2. Несколько игроков.
				```php
				$api->user([ 1249617, 134568 ]);
				```
	2. Гильдии
		1. Поиск по иду
			```php
			$api->guild('get', [ 'id' => 104 ])
			```
		2. Поиск по названию
			```php
			$api->guild('get', [ 'name' => "VimeTop" ])
			```
		3. Совпадение
			```php
			$api->guild('search', "VimeT")
			```
	3. Вывод таблицы лидеров
		1. Без сортировки
			```php
			$api->leaderboard('bw');
			```
		2. С сортировкой по убийствам
			```php
			$api->leaderboard('bw', 'kills');
			```
		3. Первые 10 записей
			```php
			$api->leaderboard('bw', 'kills', 10);
			```
		* в случае отправки запроса без аргумента, вернется список таблиц рекордов
	4. Онлайн
		1. Количество игроков онлайн
			```php
			$api->online();
			```
		2. Модераторы онлайн
			```php
			$api->online('staff');
			```
		3. Стримы, которые ведуться на данный момент
			```php
			$api->online('streams');
			```
	5. Графика
		* Возвращает ссылку на скин/плащ
		1. Скин игрока
			1. Голова размером 50px
				```php
				$api->skin("head", "LoganFrench", 50)
				```
			2. Тело 
				```php
				$api->skin("body", "LoganFrench")
				```
			3. RAW-формат
				```php
				$api->skin("raw", "LoganFrench")
				```
		2. Плащ игрока
			1. Плащ
				```php
				$api->cape("cape", "LoganFrench")
				```
			2. RAW-формат
				```php
				$api->cape("raw", "LoganFrench")
				```
	6. Дополнительно
		1. Список игр, по которым ведется статистика
			```php
			$api->misc('games');
			```
		2. Список всех возможных достижений
			```php
			$api->misc('achievements');
			```
		3. Получить информацию о игроке по токену
			```php
			$api->misc('token', "f789Ehefjhwui28");
			```
		* в случае отправки запроса без аргумента, вернётся список игр 
