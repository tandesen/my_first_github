README
===========================
I will briefly introduce several tricks I use for `sublime` in this file. In general, `sublime` is a text editor which is popular among programmers to write codes. `Sublime` is also powerful and fascinating by its conveniency and multiple plug-in modules and packages. I use `sublime` to code python from time to time. My friends love it because it is easy and fast to open and use.   

In this file, I will mainly introduce `sublime` as a text editor, and use it to write SQL codes and deal with excel files.

****

|Author|Tandesen|
|---|---
|EY_Profile|[![EY-profile]][homepage]
|Favorites|Potato and Ice-tea!


****
## Content
* [Multiple Selections](#multiple-selections)
    * Introduction
    * Activate Multiple Selection Module
    * Tricks & Examples
* [Modify Excel Files](#modify-excel-files)
    * Copy & Paste
    * Some Tips
    * Edit Transverted XML Files
* [Tricks & Plug-ins](#tricks-&-plug-ins)
    * View Bar
    * Plug-ins

## Multiple Selections
------
### Introduction
We mainly discuss writing SQL codes here. It is common to write mutiple lines of SQL codes which differ by certain words. For example, when we do qualification check, we may write `select columnA from table`, `select columnB from table` and so on. People may use excel to generate such codes by putting word `select` in one column, column names in another column, and the rest of codes in one more column. This is a good way to write codes, but one may find it difficult to maintain such codes with excel. We will discuss these issues in detail in section `Tricks & Examples`, and for that reason we need a text editor like sublime.  

Sublime(and many other text editors/IDEs) have a multiple selection mode in which we can have more than one item selected at the same time. In that mode, we can generate and maintain SQL codes in a fairly convenient way. In the following section, we gonna introduce how to activate the multiple selection mode(I will upload gif figures later).
### Activate Multiple Selection Module
There are many ways to activate the multiple selection mode. One can search that online for more details. Ways I know are as following:
```
1.Hold `CTRL` and left click on different places.
2.Click on `SHIFT + RIGHT MOUSE BUTTON`, then scroll down/up.
3.Hold `MIDDLE MOUSE BUTTON` and scroll up/down.
4.Select text fields you wanna edit and press `CTRL + SHIFT + L`.
5.For items/words selected, press `CTRL + F` and then `ALT + ENTER`.
```
One can view/add key bindings in sublime by clicking `Preferences -> Key Bindings` button and there are other ways to activate the mode.  

I find the fifth way above powerful and the reason will show up in the coming section.
### Tricks & Examples

> **Scenario1**  
Xiaohong asked Xiaoming to do data qualification check. Especially, select and count every column, group by every column. 
The client offered the header info in the `scenario1_header.txt` file. Xiaohong recommended Xiaoming to use excel to generate the SQL codes with the `text to column` function. 

That's a pretty nice way, but let us see how Xiaoming did it with sublime.

* Step1. Open the txt file with sublime.  
* Step2. Select all text and press `CTRL + SHIFT + L`, then press `LEFT ARROW BUTTON`, then press `CTRL + SHIFT + RIGHT ARROW BUTTON` to select all column names. Copy column names with `CTRL + C`.
* Step3. Open a new sublime file and enter multiple selection mode, select n lines in the meantime where n is the number of columns.
* Step4. Type `SELECT` and `CTRL + V` and whatever you want!

Some tips: when you do copy and paste for multiple lines in sublime, make sure that the line numbers from copy and paste source/destination coincide or you will get cartesian product.

> **Scenario2**  
Xiaohong asked Xiaoming to perform data analysis. Xiaohong had written part of the script as shown in `scenario2_source.txt`, and she wanted Xiaoming to generate the rest of the code as shown in `scenario2_result.txt`. Please note the tiny differences between these two text files. Generally speaking, we need to modify four parts(in first two lines and last two lines separately) among each `UNION ALL` section in `scenario2_source.txt` according to the `ALTER VIEW` section.  

I will update gif file for this part(TBC.) cuz it is cumbersome to write these steps in words.

> **Scenario3**  
Xiaoming got some results and wanted to put them in the `WHERE IN` clause. The result is:  

```
蔡文姬儿长
蔡文姬关枪
蔡文姬蛋饼
蔡文姬器猫
蔡文姬儿挺
```

And Xiaoming want to generate a SQL code like: `... WHERE IN (N'蔡文姬儿长',N'蔡文姬关枪',N'蔡文姬蛋饼',N'蔡文姬器猫',N'蔡文姬儿挺')`. While Excel can serve this, it might be quite disgusting. It's the time sublime comes into play!

* Step1. Open the txt file with sublime.  
* Step2. Perform the following key bindings in order: `CTRL + A`, `CTRL + SHIFT + L`, `'`, `LEFT ARROW BUTTON`, ``, `CTRL + SHIFT + RIGHT ARROW BUTTON` to select all column names. Copy column names with `CTRL + C`.
* Step3. Open a new sublime file and enter multiple selection mode, select n lines in the meantime where n is the number of columns.
* Step4. Type `SELECT` and `CTRL + V` and whatever you want!

--------------------------------
[csdn]:http://blog.csdn.net/guodongxiaren "我的博客"
[homepage]:https://people.ey.com/PersonImmersive.aspx?accountname=i%3A0%23%2Ef%7Cmembership%7Cmark%2Es%2Etan%40cn%2Eey%2Ecom "My real name is Tandesen! Bazinga!"
[weibo]:http://weibo.com/linpiaochen
[baidu-logo]:http://www.baidu.com/img/bdlogo.gif "百度logo"
[weibo-logo]:/img/weibo.png "点击图片进入我的微博"
[csdn-logo]:/img/csdn.png "我的CSDN博客"
[code-past]:/img/codepast-logo.jpg "公众号：编程往事"
[EY-profile]:https://img.shields.io/badge/Tandesen-EY__Profile-blue
