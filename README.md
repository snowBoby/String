# String
字符串相关操作

重要注意：字符串方法都不会修改本身值。

字符方法：charAt()、charCodeAt()
截取方法：slice()、substr()、substring() //substring会将较小的非负整数位置放前
重复方法：repeat()
自动补全方法：padStart()、padEnd()
消除空格方法：trimStart()、trimEnd()、trim() 
大小写转换方法：toLowerCase()、toUpperCase()、toLocaleLowerCase()、toLocaleUpperCase()
查找是否存在方法：indexOf(char,startSearchIndex)、lastIndexOf()、includes()、startsWith()、endsWith()
正则表达式相关方法：replace()、search()、split()、match()、matchAll()      //详细用法请看https://github.com/snowBoby/RegExp

不常用方法：
    concat()：因为+号操作符比他更简单
    localeCompare(str)：比较两个字符串，并返回1、0、-1，如果字符串在字面表中应该排在字符串参数之前则返回-1，之后1，相等0
    String.fromCharCode(字符)：他是String构造函数的方法，将字符编码转换为字符串，同charCodeAt()执行相反操作
