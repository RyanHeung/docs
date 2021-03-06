************************
Характеристики и фильтры
************************

=========================
Характеристики (features)
=========================

------------------
Типы характеристик
------------------

.. note::

    В скобках указан тип который запиcывается в базу данных.

* **Checkbox**
       
  * **Checkbox** (``C``) — простой чекбокс

  * **Multiple** (``M``) — множество чекбоксов (значение хранится в поле **variant_id** в  таблице ``cscart_product_features_values``)

* **Selectbox**

  * **Selectbox** (``S``) — простой селектбокс (**variant_id**)

  * **Numbers** (``N``) — selectbox с целыми значениями (**variant_id**)
        
  * **Brand** (``E``) — selectbox с расширенными значениями (**variant_id**)

* **Others**

  * **Text** (``T``) — текст (**value**)
        
  * **Numbers** (``O``) — числовая характеристика (**value_int**)

  * **Date** (``D``) — дата (**value_int**)

Разные значения для разных типов полей сделаны из соображений скорости и хранения данных. Раньше все характеристики хранились в текстовом виде, теперь же вариантые характеристики хранятся в виде ID. Это сделано дял ускорения работы сложных запросов, особенно в фильтрах.

------------------------
Дополнительные настройки
------------------------

* Характеристики можно группировать. Для этого есть специальный тип характеристик — Group (G). Родительская характеристика хранится в поле **parent_id**.
    
* Характеристики можно назначать к категориям — для этого есть поле **categories_path** в таблице ``cscart_product_features``.
   
* Характеристики наследуются от родительских категорий. Если прикрепить характеристику к родительской категории, она будет доступна во всех дочерних категориях.

* Product pages — показывать или не показывать характеристику на странице товара.
    
* Catalog pages — показывать или не показывать характеристику на других страницах.

=======
Фильтры
=======

Фильтры задаются по двум видам данных — характеристики и стандартные поля товара.

* Фильтры по характеристикам заполняются автоматически.

* Фильтры по стандартным полям описаны в функции ``fn_get_product_filter_fields``. В ней указаны поля по которым нужно сортировать, а также таблицы, с которыми при необходимости происходит "сцепление".
