*******
Пикеры
*******

Класс ``cePicker`` несколько изменен, по сравнению с версией 3.0.x. Теперь чтобы добавить свой пикер, нет необходимости расширять метод ``add_js_item`` с помощью JS-хука. В этот метод теперь должен передаваться массив ``placeholders`` - описание см. ниже.

.. contents::
   :backlinks: none
   :local:

===============================
Добавление выбранных элементов
===============================

``add_js_item(root_id, js_items, prefix, placeholders)``, где:

* ``root_id`` - идентификатор элемента, куда будут передаваться выбранные элементы. 
* ``js_items`` - массив выбранных элементов.
* ``prefix`` - уникальный тип пикера (c - category, p - product, a - page и т.п.).
* ``placeholders`` - массив соответствий плейсхолдеров данным в массиве ``js_items``. Возможные значения: ``%id``, ``%item``, ``%item.key``. Например:

::

  placeholders = {
      '{category_id}': '%id',
      '{category}': '%item',
  }

В этом случае предполагается, что массив ``js_items`` - типа ``key-value`` и ``%id`` будет заменен на ключ, ``%item`` - на значение ``js_items[id]``.

::

  placeholders = {
      '{category_id}': '%id',
      '{category}': '%item.value',
  }

В этом случае предполагается, что массив ``js_items`` - многомерный и ``%id`` будет заменен на ключ, ``%item.value`` - на значение ``js_items[id]['value']``.

========================
Удаление всех элементов
========================
 
``mass_delete_js_item(items_str, target_id)``, где: 

* ``items_str`` - перечень идентификаторов элементов для удаления. 
* ``target_id`` - идентификатор элемента, где хранятся удаляемые данные.

==============================
Удаление конкретного элемента
==============================

``delete_js_item(root_id, delete_id, prefix)``, где: 

* ``root_id`` - идентификатор элемента, где хранятся удаляемые данные.
* ``delete_id`` - идентификатор удаляемого.
* ``prefix`` - уникальный тип пикера.

