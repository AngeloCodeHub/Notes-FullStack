# 字串字元、編碼、正規表達式

## js String物件搭配RegExp方法

- 實務上 RegEX 通常與 String的方法 搜尋、取代、增、刪
- 場景：log 搜尋
- match()、search()、replace()、split()
- VSCode 刪除所有空行 RegEX
  利用取代並使用正規表達式(ALT+R)搜尋"^\s*(?=\r?$)\n"
  
  ```RegEX
  ^\s*(?=\r?$)\n
  ```

## FAQ

- 如何將中文字轉換為Unicode
  A：[瞭解網頁中看不懂的編碼：Unicode 在 JavaScript 中的使用](https://pjchender.blogspot.com/2018/06/guide-unicode-javascript.html)
## Bookmarks - RegEX｜String Method
### 熟讀基礎知識
- [【01】正規表示式 Regular Expression 語法規則 - 資訊人生 IT-Life](http://it-life.puckwang.com/2016/03/regular-expression.html)
- [【02】正規表示式 Regular Expression - 陳鍾誠的網站](http://ccckmit.wikidot.com/regularexpression)
- [【APP】regex101: build, test, and debug regex](https://regex101.com/)
- [【APP】RegExGPT](https://regexgpt.app/)
- [【APP】RegExr: Learn, Build, & Test RegEx](https://regexr.com/)
- [正则表达式的先行断言(lookahead)和后行断言(lookbehind) | 菜鸟教程](https://www.runoob.com/w3cnote/reg-lookahead-lookbehind.html)
- [正则表达式排除写法 - 全玉 - 博客园](https://www.cnblogs.com/mengff/p/16390372.html)
- [正則表達式-全型英數中文字、常用符號unicode對照表 | 只是個打字的](https://blog.typeart.cc/%E6%AD%A3%E5%89%87%E8%A1%A8%E9%81%94%E5%BC%8F-%E5%85%A8%E5%9E%8B%E8%8B%B1%E6%95%B8%E4%B8%AD%E6%96%87%E5%AD%97%E3%80%81%E5%B8%B8%E7%94%A8%E7%AC%A6%E8%99%9Funicode%E5%B0%8D%E7%85%A7%E8%A1%A8/)
- [正規表示式.pdf](https://www.xn--djroe106hl2fyz1bszc.online/wp-content/uploads/2025/08/%E6%AD%A3%E8%A6%8F%E8%A1%A8%E7%A4%BA%E5%BC%8F.pdf)
- [正規表示法(RegExp) 中文、英文字母、數字、特殊符號(\_)的範例；引用文章－Nathan；｜痞客邦](https://nathanmint.pixnet.net/blog/post/154247435)
- [使用 Regex 正則表達式對資料夾中的文字檔進行搜尋與取代的三種作法 | The Will Will Web](https://blog.miniasp.com/post/2023/02/02/How-to-search-and-replace-using-regex-in-3-ways)
- [淺談 regex 及其應用 - 大類的技術手記](https://marco79423.net/articles/%E6%B7%BA%E8%AB%87-regex-%E5%8F%8A%E5%85%B6%E6%87%89%E7%94%A8)
- [鳥哥私房菜 - 第十一章、正規表示法與文件格式化處理](https://linux.vbird.org/linux_basic/centos7/0330regularex.php)
- [Human-Regex: Write Readable Regular Expressions Like English - DEV Community](https://dev.to/rajibola/human-regex-write-readable-regular-expressions-like-english-1ho2)
- [Regex 教學 - 正規表示法教學 Regular Expression Tutorial](https://www.fooish.com/regex-regular-expression/)
- [Regular Expression-正規表達式教學，使用狀態機輔助說明-基礎篇](https://hengxiuxu.blogspot.com/2017/10/regular-expression.html)
- [visual studio code - VSCode: delete all comments in a file - Stack Overflow](https://stackoverflow.com/questions/50574731/vscode-delete-all-comments-in-a-file)
### Javascript 應用
- [Assertions - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions/Assertions)
- [Character escape: \\n, \\u{...} - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Character_escape)
- [ChatGPT X JavaScript精選15堂課:輕鬆學會網頁程式設計實作](https://ksml.ebook.hyread.com.tw/bookDetail.jsp?id=356823)
- [JavaScript Regex Cheat Sheet Tech The World | Facebook](https://www.facebook.com/100064815188039/posts/912881614215670)
- [Lookahead assertion: (?=...), (?!...) - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Lookahead_assertion)
- [RegExp - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp)
- [Regular expressions - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions)
- [String - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
### Powershell 應用
- [30天挑戰精通PowerShell : Windows、Linux和macOS適用](https://webpacx.ksml.edu.tw/bookDetail/1775845)
- [正規表示法 Sample - 點部落](https://dotblogs.com.tw/bcsddaroka1/2013/01/07/86834)

  

[about\_Comparison\_Operators - PowerShell | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-7.5)

  

[about\_Regular\_Expressions - PowerShell | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_regular_expressions?view=powershell-7.5)

  

[dotNET Regular Expressions - .NET | Microsoft Learn](https://learn.microsoft.com/en-us/dotnet/standard/base-types/regular-expressions)

  

[How to Use PowerShell Replace to Replace Text \[Examples\]](https://adamtheautomator.com/powershell-replace)

  

[PowerShell and Regex: A Comprehensive Guide](https://adamtheautomator.com/powershell-regex/)

  

[Powershell: The many ways to use regex](https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression)

  

[Regular Expression 正則表達式 | 炎龍牙 - 點部落](https://dotblogs.com.tw/dragoncancer/2015/12/03/153024)

  

[Regular Expression Language - Quick Reference - .NET | Microsoft Learn](https://learn.microsoft.com/en-us/dotnet/standard/base-types/regular-expression-language-quick-reference)

  

[Select-String (Microsoft.PowerShell.Utility) - PowerShell | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/select-string?view=powershell-7.5)

  

### UTF-8

  

[豬腦爸 D NOW BA: ANSI和Unicode、UTF-8和UTF-16、BOM](https://dnowba.blogspot.com/2012/07/ansiunicodeutf-8utf-16bom.html)

  

[瞭解網頁中看不懂的編碼：Unicode 在 JavaScript 中的使用 ~ PJCHENder](https://pjchender.blogspot.com/2018/06/guide-unicode-javascript.html)

  

[BOM BOM BOM | 就是愛程式](https://atedev.wordpress.com/2007/09/19/bom-bom-bom)

  

[HowTo: UNIX / Linux Convert DOS Newlines CR-LF to Unix/Linux Format - nixCraft](https://www.cyberciti.biz/faq/howto-unix-linux-convert-dos-newlines-cr-lf-unix-text-format)

  

- [Unicode、UTF-8、UTF-16？編碼格式花傻傻⋯⋯ - Open Our Oprate Occupied](https://alrin0000.blogspot.com/2014/03/unicodeutf-8utf-16.html)
- [Unicode/UTF-8的差異](https://dotblogs.com.tw/jimmyyu/2009/08/18/10113)
- [UTF-8 BOM (Byte Order Mark) 的問題 @新精讚](http://n.sfs.tw/content/index/10053)

  

[VS中無簽名UTF8和帶簽名UTF8格式 - 壹讀](https://read01.com/zh-tw/3GNP52.html)

  

[Unicode – The World Standard for Text and Emoji](https://home.unicode.org/)