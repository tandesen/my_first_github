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
fuzz.ratio('')
```

--------------------------------
[homepage]:https://people.ey.com/PersonImmersive.aspx?accountname=i%3A0%23%2Ef%7Cmembership%7Cmark%2Es%2Etan%40cn%2Eey%2Ecom "My real name is Tandesen! Bazinga!"
[EY-profile]:https://img.shields.io/badge/Tandesen-EY__Profile-blue
[Contact]:https://img.shields.io/badge/Wechat-markts28-brightgreen "Add me beauties!"

