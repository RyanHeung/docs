*******
Дебагер
*******

В CS-Cart встроен дебагер. С его помощью можно получить информацию об HTTP- и SQL-запросах, шаблонах страниц, настройках сервера и т.п.

Узнать, что дебагер включен, можно по иконке жучка в правом верхнем углу экрана. Если нажать на иконку, появится панель отладчика.

========================
Как включить и выключить
========================

---------
Постоянно
---------

В файле **config.local.php** или **local_conf.php** вставить строчку::

   define('DEBUG_MODE', true); 

В этом случае дебагер будет работать всегда и везде. Отключить его можно, заменив *true* на *false*, или совсем убрав определение константы.

--------
Временно
--------

1. Войти в панель администратора как root-администратор.

2. В URL дописать параметр ``debug``, например::

    http://example.com/admin.php?debug

Так дебагер включится только для данной сессии. Чтобы выключить его, наведите курсор на логотип CS-Cart на панели дебагера вверху. Чуть левее логотипа появится кнопка выключения.

----------
На витрине
----------

Если витрина находится на том же домене, что и панель администратора, дебагер будет включен вместе с включением в панели администратора. 

Для витрин с другим доменом надо в URL витрины дописать ``debug=*debugger_id*``. Узнать ``debugger_id`` можно в панели администратора: там ID отображается в нижней части панели дебагера.

Если при включенном дебагере выйти из учетной записи в панели администратора, то дебагер выключится и в панели администратора, и на витрине.

===============
Секции дебагера
===============

------
Server
------

Вся информация о сервере (распечатка ``phpinfo()``).

-------
Request
-------

Информация о полученных данных от клиента. В часности, распечатка переменных:

* ``$_REQUEST``

* ``$_SERVER``

* ``$_COOKIE``

------
Config
------

Вывод переменной ``config``, ``settings`` и ``runtime``, т.е. данные, относящиеся к настройке магазина.

---
SQL
---

Список всех SQL-запросов, отправленных в БД при генерации страницы. 

Здесь имеются 3 вкладки:
 
1. Список запросов по порядку их выполнения и временем их выполнения. При клике по запросу переходим на 3 вкладку. 

2. Список запросов, групприванных по повторениям. По каждому запросу имеется информация по колличеству повторений, минимальное, максимальное и среднее время выполнения среди повторений. 

3. Песочница для экспериментов с запросами. Отправив SQL-запрос, получаем: 

   * время его выполнения;

   * вывод ``EXPLAIN`` для ``SELECT`` запросов;

   * результат запроса;

   * вывод backtrace при клике на запрос из первой вкладки.

-------
Logging
-------

Вывод некоторой информации между контрольными точками. Выдается информация:

* **Memory** — использование памяти

* **Files** — количество включенных файлов
    
* **Queries** — количество выполненных запросов
    
* **Time** — затраченное время

В скобках указывается общее значение.

---------
Templates
---------

Список включенных шаблонов в виде дерева и список переменных, которые были назначены в Smarty до рендера шаблонов.

============================
Нижняя часть панели дебагера
============================

* **Page generating time** — время генерации страницы на стороне сервера.

* **Memory usage** — количество затраченной памяти сервера на генерацию страницы.

* **Session size** — размер сессии пользователя.

* **Clear session** — очистка кеша профайлера из сессии.
