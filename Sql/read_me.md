README
================================
该部分意旨提供FTDS平日所需sql知识的练习题。随着`德森大老爷`的成长题目持续更新。data来源于非项目。  
以上都是bullshit，鲁迅说我没有说过。现在是2022年，来自未来的我，时光如此穿梭，行走在曼妙银河，抬头向着星空 大声说：我就是帅！:sunglasses:
****

|作者|德森大老爷|
|---|---


****  
## 排序指定选位置选择的若干事  
```
1. SELECT TOP N Column1, Column2 FROM Table1 ORDER BY balabala  
2. SELECT Column1, Column2 FROM Table1 ORDER BY balabala LIMIT 2,1 #tip1: LIMIT m,n: m指的是从第几行开始，m可为0.n指的是从m往后选几行。tip2: ORDER BY clause要在LIMIT前面。  
3. 窗口函数[1]: SELECT DENSE_ROW() OVER(PARTITION BY Column1 ORDER BY Column2 DESC) RANK, Column2 FROM Table1 #SQL RANK FUNCs[2]  
```
[1][窗口函数](https://zhuanlan.zhihu.com/p/92654574)
[2][排序函数们](https://www.sqlshack.com/overview-of-sql-rank-functions/)

## SQL语句的书写顺序与执行顺序  
网上有很多资料，[如这个](https://zhuanlan.zhihu.com/p/77847158)。  
```
(8) SELECT (9)DISTINCT<Select_list>
(1) FROM <left_table> (3) <join_type>JOIN<right_table>
(2) ON<join_condition>
(4) WHERE<where_condition>
(5) GROUP BY<group_by_list>
(6) WITH {CUBE|ROLLUP}
(7) HAVING<having_condtion>
(10) ORDER BY<order_by_list>
(11) LIMIT<limit_number>
```
理解这个事情很重要，可以明白一些编码时的问题，如我在`SELECT`语句里面给Column编辑了别名，在下面的`WHERE`语句中不能用这个别名，但在`ORDER BY`中就可以用这个别名，因为语句执行顺序问题。
