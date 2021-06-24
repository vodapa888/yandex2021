# yandex2021

# Задание 1

1)

select AVG(case when promocode_id is null then 0 else 1 end) as promo_avg
from orders

2)

SELECT b.name as pop_promo, count(a.promocode_id) as num_promo
FROM orders as a
left join promocodes as b 
on a.promocode_id = b.promocode_id
GROUP BY a.promocode_id
ORDER BY count(*) DESC
LIMIT 1;
