Readme
=======================
The general idea is to use python (requests package) to get the source code of web page (html file), and parse the html file in order to get useful information. There are several ways to parse the html file using python, including regular expression, xpath (which we will use in this document) & css selector, certain packages such as selenium & BeautifulSoup, etc. This document describes a concrete example that I use to scraw douyin live info.  
Please use chrome browser as you follow this document.

****

## Content
* [html_in_general](#html_in_general)
* [source_code_for_the_first_time](#source_code_for_the_first_time)
* [issues_and_modifications](#issues_and_modifications)

----------------------

html_in_general
------
Open a website ([https://live.douyin.com/](https://live.douyin.com/)), press `ctrl + u` to open its source file in a new window, or press `fn + F10` to open the developer tools.  

`ctrl + u`  open html source files.  
`fn + F10`  open developer tools.  
`ctrl + shift + l`  open developer tools.
