Assist
------

Описание
========

Провайдер электронных платежей.

Официальный сайт: |link|

.. |link| raw:: html

   <!--noindex--><a href="http://www.assist.ru/" target="_blank" rel="nofollow">Assist</a><!--/noindex-->

ASSIST предлагает услуги:

*   Приема платежей по кредитным картам популярных во всем мире платежных систем (VISA, MasterCard, JCB, DCI);

*   Приема платежей по электронной наличности самых популярных систем рунета (WebMoney, Яндекс.Деньги, QIWI) в рамках единого пользовательского интерфейса. При заключении договора можно выбрать необходимый набор электронных платежных средств;

*   Приема платежей по электронной наличности для нерезидентов России (WebMoney, Яндекс.Деньги, QIWI) Услуга предоставляется в рамках единого пользовательского интерфейса при условии открытия нерезидентом счета типа "К" в любом из уполномоченных банков РФ;

*   Расширенный мониторинг транзакций по кредитным картам;

Возможности Assist:

*   Изменение дизайна платежных страниц;

*   Двустадийный механизм работы (авторизация кредитной карты и финансовое подтверждение);

*   Возможность оплаты по кредитной карте с использованием Assist®ID;

*   Интерактивная WEB-POS-авторизация;

*   Получение выписок по операциям (в онлайновом режиме и по электронной почте);

*   Отмены и возвраты в режиме онлайн (void, reversal, refund);

*   Организация системы мотивации и поощрения клиентов.


Инструкция
==========

1.  Зарегистрируйте интернет-магазин в системе Assist.

    Для корректной работы платежного модуля "Assist" Вам нужно активировать опцию "Перейти по URL для возврата".

    .. fancybox:: img/assist_return.png
        :alt: Assist return

    URL_RETURN передается модулем при выполнении платежа. Поэтому в полях URL_RETURN можете указать домен магазина. А URL_RETURN_OK оставить пустым.

    Настройку отправки результатов платежей необходимо оставить пустым.

    .. fancybox:: img/assist_notify.png
        :alt: Assist notify

2.  Создайте новый способ оплаты (:doc:`Способы оплаты <adding_payment>`).

3.  Выберите процессор оплаты "Assist" в окне редактирования способа оплаты.

    .. fancybox:: img/assist_create.png
        :alt: Assist

4.  Пройдите во вкладку "Настроить" нового способа оплаты и выполните настройку.

    .. fancybox:: img/assist_settings.png
        :alt: Assist

    Доступные настройки:

    *   ID аккаунта;

    *   Логин;

    *   Пароль;

    *   Язык;

    *   Тестовый/рабочий режим;

    *   URL провайдера — URL для подключения к серверам провайдера платежей ASSIST;
        
        .. note::
          
            Поле "URL провайдера" впервые появилось в CS-Cart 4.6.3.

    *   Префикс заказа;

    *   Секретное слово (Берется из "Настройки отправки результатов платежа" личного кабинета Assist).

5.  Проверьте работу создав тестовый заказ.

