установка из Дистрибутивы для PHP -> Малый бизнес  
https://www.1c-bitrix.ru/download/cms.php#tab-section-3

small_business_encode (1).zip

Параметры базы данных
Сервер: localhost
Пользователь: Новый
Имя пользователя: sitemanager3
Пароль: site1234
База данных: Новая
*Новая база данных: dbbitrix03


Тип таблиц: стандартный

Параметры администратора базы данных
*Логин: root
Пароль:

Дополнительные параметры
Права доступа к файлам: 0664
Права на доступ к папкам сайта 0755



виснет при установке модуля "Сайты 24"
//Сообщение
Внимание! На данном шаге произошла ошибка установки продукта. Повторите установку текущего шага. В случае повторения ошибки пропустите шаг. [Bitrix\Main\DB\SqlQueryException] Mysql query error: (2006) MySQL server has gone away (400) SELECT * FROM b_cache_tag WHERE TAG = 'landing_blocks'
//Решение
В процессе выполнения запроса сервер оборвал соединение. Проблема связана с настройкой MySQL и часто возникает когда на сервере установлен небольшой лимит времени на соединение. Установите в bitrix/php_interface/after_connect.php:
$DB->Query("SET wait_timeout=28800");


* Логин (мин. 3 символа):	
admin
* Пароль (мин. 6 символов):	
123456
* Подтверждение пароля:	
123456	
* E-Mail:1@m.ru	
Имя:	
Фамилия:

Интеренет-магазин
Адаптивный шаблон Bootstrap 4
1.Зелено-бирюзовый
Информация о сайте: Название: Современная одежда+
	Все по дефолту
Складской учет включен
Инфо о магазине по дефолту
Типы плательщиков по дефолту и физ. и юр.лица
Далее по дефолту



НЕ ДЕЛАЛ---
---------------------------------------------
Сбросил пробный период до одного дня:
Открывает файл /bitrix/modules/main/include.php (предварительно сохранить копию)
Заменить:
$GLOBALS[___1958990961(118)] = OLDSITEEXPIREDATE;
На:
$GLOBALS[___1958990961(118)] = time()+86400*1; //заменили OLDSITEEXPIREDATE
