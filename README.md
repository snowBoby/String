# String
字符串相关操作，重要注意：字符串方法都不会修改本身值。

* 字符串和数组的确很相似，他们都是类数组，都有length属性以及indexOf(..)和concat(..)方法。
* JavaScript中字符串是不可变的，而数组是可变的。字符串不可变是指字符串的成员函数不会改变其原始值，而是创建并返回一个新的字符串。而数组的成员函数都是在其原始值上进行操作。例子如下
* 许多数组函数来处理字符串很方便。虽然字符串没有这些函数，但是可以通过“借用”数组（Array.prototype.xxx.call）的非变更方法(操作数组原始值的成员函数eg：reverse() )来处理字符串。例子如下

## String实例常用方法：
* 字符方法：charAt()、charCodeAt()
* 截取方法：slice()、substr()、substring() //substring会将较小的非负整数位置放前
* 重复方法：repeat()
* 自动补全方法：padStart()、padEnd()
* 消除空格方法：trimStart()、trimEnd()、trim() 
* 大小写转换方法：toLowerCase()、toUpperCase()、toLocaleLowerCase()、toLocaleUpperCase()
* 查找是否存在方法：indexOf(char,startSearchIndex)、lastIndexOf()、includes()、startsWith()、endsWith()
* 正则表达式相关方法：replace()、search()、split()、match()、matchAll()      //[详细用法](https://github.com/snowBoby/RegExp)
* 不常用方法：
    * concat()：因为+号操作符比他更简单
    * localeCompare(str)：比较两个字符串，并返回1、0、-1，如果字符串在字面表中应该排在字符串参数之前则返回-1，之后1，相等0
    * String.fromCharCode(字符)：他是String构造函数的方法，将字符编码转换为字符串，同charCodeAt()执行相反操作

```
var a = "foo"; 
var b = ["f","o","o"];

a[1] = "O"; //a[1]在JavaScript中并非总是合法语法，在老版本的IE中就不被允许（现在可以了）。正确的方法应该是a.charAt(1)。
b[1] = "O"; 

a; // "foo" 
b; // ["f","O","o"]

//字符串不可变，数组可变，体现在如下：
c = a.toUpperCase(); 
a === c;    // false 
a;          // "foo" 
c;          // "FOO" 

b.push( "!" ); 
b;          // ["f","O","o","!"]

//可以通过“借用”数组的非变更方法来处理字符串
a.join;         // undefined 
a.map;          // undefined 

var c = Array.prototype.join.call( a, "-" ); 
var d = Array.prototype.map.call( a, function(v){     return v.toUpperCase() + "."; } ).join( "" ); 

c;              // "f-o-o" 
d;              // "F.O.O."

//修改原始值的数组成员函数，字符串不能“借用”
a.reverse;      // undefined 
b.reverse();    // ["!","o","O","f"] 
b;              // ["f","O","o","!"]
Array.prototype.reverse.call( a ); //报错，我们无法“借用”数组的可变更成员函数，因为字符串是不可变的。

*注意：如果需要经常以字符数组的方式来处理字符串的话，倒不如直接使用数组。这样就不用在字符串和数组之间来回折腾。可以在需要时使用join("")将字符数组转换为字符串
```

