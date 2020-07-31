README
===========================

****

|Author|Tandesen|
|---|---
|EY_Profile|[![EY-profile]][homepage]
|Favorites|Potato and Ice-tea!
|Contact|![Contact]


For fuzzy match, I use [fuzzywuzzy package](https://pypi.org/project/fuzzywuzzy/) which is based on the [levenshtein distance](https://en.wikipedia.org/wiki/Levenshtein_distance). There are [many other ways/packages](https://zhuanlan.zhihu.com/p/32929522) for fuzzy match. Here we mainly introduce the fuzzywuzzy package.  

Fuzzywuzzy package contains several methods, which you can find on [this blog](https://chairnerd.seatgeek.com/fuzzywuzzy-fuzzy-string-matching-in-python/) or [github page](https://github.com/seatgeek/fuzzywuzzy).   

For my position, I usually deal with Chinese strings and mainly use the `ratio` method(recently I realize that I should use `partial_ratio` method. I will discuss this issue latter) when doing fuzzy match. These methods might be origionally designed for matching English characters. When dealing with Chinese characters, one should be probably interested in the [`Soundex Algorithm`](https://blog.csdn.net/chndata/article/details/41114771) which is based on the pronunciation.

I wanna discuss two things here, the first one is the issue in the bracket in the previous paragraph. The second issue is the data preprocessing when we do fuzzy match.

1. `ratio` & `partial_ratio`
```Python
from fuzzywuzzy import fuzz
fuzz.ratio('齐齐哈尔市甘南县甘南镇富裕村大兴屯路南','甘南镇富裕村大兴屯路南')
Out[1]: 73
fuzz.partial_ratio('齐齐哈尔市甘南县甘南镇富裕村大兴屯路南','甘南镇富裕村大兴屯路南')
Out[2]: 100
```  
In some project I do fuzzy match between places. I should use `partial_ratio` instead of `ratio` in this project.

2. Data preprocessing
```Python
from fuzzywuzzy import fuzz
fuzz.ratio('冰水有限公司','切尔西有限公司')
Out[3]: 62
fuzz.ratio('冰水','切尔西')
Out[4]: 0
```  
In some project I do fuzzy match between companies. [I should clean data and cut `有限公司` in the origional data.](https://zhuanlan.zhihu.com/p/32929522) 

--------------------------------
[homepage]:https://people.ey.com/PersonImmersive.aspx?accountname=i%3A0%23%2Ef%7Cmembership%7Cmark%2Es%2Etan%40cn%2Eey%2Ecom "My real name is Tandesen! Bazinga!"
[EY-profile]:https://img.shields.io/badge/Tandesen-EY__Profile-blue
[Contact]:https://img.shields.io/badge/Wechat-markts28-brightgreen "Add me beauties!"

