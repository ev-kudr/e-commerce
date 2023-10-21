# Аналитическое исследование: E-commerce  
EDA, cohort analysis, retention, RFM-segmentation

### Цель исследования
Изучить поведение пользователей интернет-магазина и особенности работы службы доставки   

### Входные данные:

Для иследования было предоставлено 3 csv-файла с информацией о пользователях, заказах и товарных позициях, заказанных покупателями:

- `olist_customers_datase.csv` — таблица с уникальными идентификаторами пользователей
    - `customer_id` — позаказный идентификатор пользователя
    - `customer_unique_id` —  уникальный идентификатор пользователя  (аналог номера паспорта)
    - `customer_zip_code_prefix` —  почтовый индекс пользователя
    - `customer_city` —  город доставки пользователя
    - `customer_state` —  штат доставки пользователя  
    
- `olist_orders_dataset.csv` —  таблица заказов
    - `order_id` —  уникальный идентификатор заказа (номер чека)
    - `customer_id` —  позаказный идентификатор пользователя
    - `order_status` —  статус заказа
    - `order_purchase_timestamp` —  время создания заказа
    - `order_approved_at` —  время подтверждения оплаты заказа
    - `order_delivered_carrier_date` —  время передачи заказа в логистическую службу
    - `order_delivered_customer_date` —  время доставки заказа
    - `order_estimated_delivery_date` —  обещанная дата доставки  
    
- `olist_order_items_dataset.csv` —  товарные позиции, входящие в заказы
    - `order_id` —  уникальный идентификатор заказа (номер чека)
    - `order_item_id` —  идентификатор товара внутри одного заказа
    - `product_id` —  ид товара (аналог штрихкода)
    - `seller_id` — ид производителя товара
    - `shipping_limit_date` —  максимальная дата доставки продавцом для передачи заказа партнеру по логистике
    - `price` —  цена за единицу товара
    - `freight_value` —  вес товара

Уникальные статусы заказов в таблице `olist_orders_dataset`:

    - created —  создан
    - approved —  подтверждён
    - invoiced —  выставлен счёт
    - processing —  в процессе сборки заказа
    - shipped —  отгружен со склада
    - delivered —  доставлен пользователю
    - unavailable —  недоступен
    - canceled —  отменён

### Задачи исследования:

 - Определено число пользователей, совершивших покупку только один раз.
 - Определено среднее число заказов в месяц, которое не доставляется до покупателя. Приведена детализация по причинам.
 - Для каждого товара определено, в какой день недели чаще всего покупается этот товар.
 - Для каждого пользователя определено среднее число покупок в неделю (по месяцам)
 - Проведен когортный анализ пользователей.
 - Построена RFM-сегментация пользователей.

### Характеристика отчета:
- Исследование выполено на языке программирования Python.
- В ходе работы использованы библиотеки pandas, numpy, scipy.stats, seaborn, matplotlib.
- В ходе исследования выполнен предварительный анализ данных (EDA), проведен когортные анализ пользователей (оценка retention по когортам), проведена RFM-сегментация пользователей.
- Исследование представляет собой 6 аналитических задач, направленных на изучение аудитории интернет-магазина и работы службы доставки. В конце аналитического отчета сделаны общие выводы.