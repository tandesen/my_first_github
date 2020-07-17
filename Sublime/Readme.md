README
===========================
I will briefly introduce several tricks I use for `sublime` in this file. In general, `sublime` is a text editor which is popular among programmers to write codes. `Sublime` is also powerful and fascinating by its conveniency and multiple plugin modules and packages. I use `sublime` to code python from time to time. My friends love it because it is easy and fast to open and use.   

In this file, I will mainly introduce `sublime` as a text editor, and use it to write SQL codes as well as dealing with excel files.

****

|Author|Tandesen|
|---|---
|EY_Profile|[![EY-profile]][homepage]
|Favorites|Potato and Ice-tea!
|Contact|![Contact]


****
## Content
* [Multiple Selections](#multiple-selections)
    * Introduction
    * Activate Multiple Selection Mode
    * Tricks & Examples
* [Modify Excel Files](#modify-excel-files)
    * Introduction
    * Copy & Paste
    * Edit Transverted XML Files
* [Settings & Plugins](#settings--plugins)
    * Settings
    * Plugins

## Multiple Selections
### Introduction
We mainly discuss writing SQL codes here. It is common to write multiple lines of SQL codes which differ by certain words. For example, when we do qualification check, we may write `select columnA from table group by columnA`, `select columnB from table group by columnB` and so on. People may use Excel to generate such codes by putting word `select` in one column, column names in another column and so on. This is a good way to write codes, but one may find it difficult to maintain such codes with Excel. We will discuss these issues in detail in section `Tricks & Examples`, and for that reason we need a text editor like sublime.  

Sublime and many other text editors/IDEs have a multiple selection mode in which we can have more than one item selected at the same time. In this mode, we can generate and maintain SQL codes in a fairly convenient way. In the following section, we gonna introduce how to activate the multiple selection mode
**(I will upload gif figures later)**.
### Activate Multiple Selection Mode
There are many ways to activate the multiple selection mode. Ways I know are as following:
```
1.Hold `CTRL` and left click on different places.
2.Click on `SHIFT + RIGHT MOUSE BUTTON`, then scroll down/up.
3.Hold `MIDDLE MOUSE BUTTON` and scroll up/down.
4.Select text fields you wanna edit and press `CTRL + SHIFT + L`.
5.For items/words selected, press `CTRL + F` and then `ALT + ENTER`.
```
One can view/add key bindings in sublime by clicking `Preferences -> Key Bindings` buttons. I find the fifth way above super powerful and the reasons will show up in the coming section.
### Tricks & Examples

It is always helpful to use shortcut keys. Except for key bindings in sublime, one should also be familiar with the following shortcut keys, which can also be used in many other softwares other than sublime:
```
1.`CTRL + RIGHT/LEFT ARROW`: Move cursor over words or delimiters in English and phrases in Chinese.
2.`CTRL + SHIFT + RIGHT/LEFT ARROW`: Move and select over words or phrases.
3.`HOME/END`: Move cursor to the beginning/end of that line.
4.`CTRL + HOME/END`: Move cursor to the beginning/end of the entire file.
5.`SHIFT` plus shortcut keys in 3 and 4: Move and select.
```

Now let us see some examples where we can apply everything we have acquired so far.

> **Scenario1**  
Xiaohong asked Xiaoming to do data qualification check. Especially, select and count every column, group by every column. 
The client offered the header info in the `scenario1_header.txt` file. Xiaohong recommended Xiaoming to use excel to generate the SQL codes with the `text to column` function. 

That's a pretty nice way, but let us see how Xiaoming did it with sublime.

* Step1. Open the txt file with sublime.  
* Step2. Select all text and press `CTRL + SHIFT + L`, then press `LEFT ARROW BUTTON`, then press `CTRL + SHIFT + RIGHT ARROW BUTTON` to select all column names. Copy column names with `CTRL + C`.
* Step3. Open a new sublime file and enter multiple selection mode, select n lines in the meantime where n is the number of columns.
* Step4. Type `SELECT` and `CTRL + V` and whatever you want!

**Tips**: when you do copy and paste for multiple lines in sublime, make sure that the line numbers from copy and paste source/destination coincide or you will get cartesian product.

> **Scenario2**  
Xiaohong asked Xiaoming to perform data analysis. Xiaohong had written part of the script as shown in `scenario2_source.txt`, and she wanted Xiaoming to generate the rest of the code as shown in `scenario2_result.txt`. Please note the tiny differences between these two text files. Generally speaking, we need to modify four parts(in the first two lines and last two lines separately) among each `UNION ALL` section in `scenario2_source.txt` according to the `ALTER VIEW` section.  

I will update gif files for this part(TBC.) cuz it is cumbersome to write these steps in words.

> **Scenario3**  
Xiaoming got some results and wanted to put them in the `WHERE IN` clause. The result is:  

```
蔡文姬儿长
蔡文姬关枪
蔡文姬蛋饼
蔡文姬器猫
蔡文姬儿挺
```

> And Xiaoming want to generate a SQL code like: `... WHERE IN (N'蔡文姬儿长',N'蔡文姬关枪',N'蔡文姬蛋饼',N'蔡文姬器猫',N'蔡文姬儿挺')`. While Excel can serve this, it might be quite disgusting. It's when sublime comes into play!

* Step1. Open a new file in sublime and copy paste the result.  
* Step2. Perform the following key bindings in order: `CTRL + A`, `CTRL + SHIFT + L`, `'`, `HOME`, `N`, `END`, `,`, `HOME`, `BACKSPACE`, `END`, `BACKSPACE`, `CTRL + A`, `(`. Note that Chinese input methods will cause problems!

## Modify Excel Files
### Introduction
One can modify excel files by programming. However, it is convenient to do that with a text editor like sublime sometimes. As far as I know, one way is to copy & paste content in excel into sublime as plain text, the other way is to convert excel file into XML file and modify it with sublime. We will introduce these two methods in the next two sections.
### Copy & Paste
Copy and paste content in excel files to sublime and cope with plain text. Please refer to `Excel_copy_&_paste.xlsx`. We want to create tab `result` from tab `origin` with tab `reference`.  
Some tips you should know when dealing with plain text from excel files:

* Line break issues could be quite annoying. If you have multiple lines and want to put them in one cell in Excel, please use `"` to wrap these lines. It might also be helpful for you to check `column to text` function in Excel occasionally to make sure which delimiters are being used.

* When it comes to delimiter, please note that the `spaces` you see in sublime may not actually be the same. Typically, select spaces in sublime, `·` denotes `space` and `——` denotes `tab`.

* Copy and paste content with filter in Excel may cause troubles. Sometimes you wanna copy/paste content from/to visible/invisible cells in excel but get different results. I was struggling with some of the issues and failed to find a perfect solution. Here are some links for you to refer:   
[复制粘贴到筛选单元格里](http://club.excelhome.net/thread-861292-1-1.html "MarkMarkMark!")  
[复制筛选后的内容](https://zhuanlan.zhihu.com/p/29831730 "ChinaChinaChina!!")  
[复制粘贴筛选后的单元格](https://jingyan.baidu.com/article/b87fe19ec22a2312183568cf.html "DoingDoingDoing!!!")  

### Edit Transverted XML Files
Extensible Markup Language (XML) is a markup language, the design goals of XML emphasize simplicity, generality, and usability across the Internet[(1)](#references). 
XML files can be opened in different operating systems and versions of softwares without conflicts, which makes it popular.  

In our case, save your excel file in `XML Spreadsheet 2003(*.XML)` format and open it with sublime(`XML Data(*.XML)` format doesn't work and I haven' find out the reason). There are abundant information contained in the XML file for you to explore such as the format of Excel file and tab names. Now just perform your favorite tricks in multiple selection mode! For example, if you wanna modify all tab names in the meantime you can select and find all markups `<Worksheet ss:Name="">` and type or paste sheetnames you have in mind. Finally, just open the XML file with Excel after editing and save it back to `*.xlsx` format.  

Be careful:bell:! I haven't carefully checked whether we will lose information by saving Excel in XML format, especially for formula, link or picture information. But I believe that this method works for plain text information contained in Excel.

## Settings & Plugins
### Settings
Maybe we should introduce this part in the very beginning of this file. Anyway, I do recommend that you explore tool bars when you install a new software, especially for key bindings. I found some functions pretty useful in the tool bars of sublime:  
* `View -> Syntax`: Choose the syntax and enjoy the wonderful format & color!
* `View -> Layout`: Pretty useful when you deal with multiple files at the same time.
* `View -> Spell Check`: Say no more! Always useful.
* `View -> Word Wrap`: Can be tricky when combined with multiple selection mode. Be careful!
* `CTRL + K -> CTRL + U`: Change selected characters to upper case.
* `CTRL + K -> CTRL + L`: Change selected characters to lower case.
* `Preferences -> Package Control : Install Package`: Where we download packages(plugins)!

### Plugins
Download the following packages via the last bullet in `Settings` section. After doing so, follow the command after colon and explore more!
* `SqlBeautifier`: Select your SQL codes and press `CTRL + K`, `CTRL + F` to format your SQL codes.

## References
### (1): [https://en.wikipedia.org/wiki/XML](https://en.wikipedia.org/wiki/XML)
--------------------------------
[homepage]:https://people.ey.com/PersonImmersive.aspx?accountname=i%3A0%23%2Ef%7Cmembership%7Cmark%2Es%2Etan%40cn%2Eey%2Ecom "My real name is Tandesen! Bazinga!"
[EY-profile]:https://img.shields.io/badge/Tandesen-EY__Profile-blue
[Contact]:https://img.shields.io/badge/Wechat-markts28-brightgreen "Add me beauties!"
