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
