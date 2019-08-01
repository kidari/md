1. 不要左模糊
2. 不要用null扫描可用置0判断
3. 不要使用or可用union all
4. 不要在使用!=或<>操作符
5. 对查询进行优化，应尽量避免全表扫描，首先应考虑在 where 及 order by 涉及的列上建立索引。
6. in 和 not in 也要慎用，否则会导致全表扫描，如：
select id from t where num in(1,2,3)
7. 对于连续的数值，能用 between 就不要用 in 了：
select id from t where num between 1 and 3
8. 应尽量避免在 where 子句中对字段进行表达式操作，这将导致引擎放弃使用索引而进行全表扫描。如：
select id from t where num/2=100
应改为:
select id from t where num=100*2
9. 一个表的索引数最好不要超过6个，若太多则应考虑一些不常使用到的列上建的索引是否有 必要。
10. 