# Požadavek 1: Account manager potřebuje pro svého inzerenta s ID 123 výpis
jeho reklam s počtem jejich zobrazení, prokliků, cenou za prokliky, počtem
konverzí a jejich souhrnnou hodnotou.



select il.impression_id, cl.cpc, count(cl.impression_id) as proklik, sum(conl.valuess) as konverze 
from impression_logs il
join click_logs cl on cl.impression_id = il.impression_id
join conversion_logs conl on conl.impression_id = il.impression_id
where il.impression_id = 123
group by il.impression_id, cl.cpc
order by cl.cpc desc

Požadavek 2: Yield manager potřebuje výpis 10 zón s nejvyšší průměrnou
cenou za proklik reklamy.

Bohužel sjem neudělal
