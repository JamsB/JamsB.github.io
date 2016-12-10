---
title: JavaScript apply与call 的使用
date: 2016-08-21 12:00:19
tags:
- javascript
- apply
- call
- js
- 前端
---

前几天在网上看了看了js `call` 的使用，有点犯迷糊，今天正好看书看到了这边，顺便记录一下,水平有限，对js也没有自己的理解，基本是摘抄原文。主要是自己做个记录，二来是测试一下Hexo的markdown语法，各位看官不要介意，虽然我知道，不一定有人来看，全当我自说自话。

### 定义
>在Function对象中包含apply与call这两种方法，通过他们调用的函数的this引用，可以指向任意特定的对象。也就是说，可以理解为它们能够显性地指定接收方对象。
<!--more-->

下面是一个使用了apply方法与call方法得例子。
{% codeblock lang:javascript  %}
function f() { console.log(this.x) };
var obj = { x:4  };
f.apply(obj); //通过apply调用函数f。函数内的this引用了对象obj;
>4
f.call(obj);  //同理，结果也是4;
>4

//将接收方对象指定为另一个对象并进行调用
var obj = {
x:3,
doit: function(){ console.log('method is called. '+ this.x); }
};
var obj2 { x:4 };
obj.doit.apply(obj2);
>method is called. 4
{% endcodeblock  %}

### 参数传递方式
>对Funtion对象f使用apply与call方法，就能调用该函数。不考虑函数内this引用的话，这和f()的方法是一样的。两者的区别被调用函数（方法）内this引用，this引用的是作为apply/call的第一个参数被传递的对象。而apply与call不同之处在于对其他参数的传递方式。对于apply来说，剩余参数将使用数组来传递而call是直接原样传递形参。

下面是call与apply传递其它参数的例子
{% codeblock lang:javascript %}
function f(a,b) { console.log('this.x = ' + this.x + ',a='+a+',b='+b+'') }
f.apply({x:4},[1,2]); //从第二个参数开始数列中的元素都是函数f的参数
>this.x=4,a=1,b=2
f.apply({x:4},1,2);  //从第二个参数开始都是函数f的参数
>this.x=4,a=1,b=2
{% endcodeblock %}
在实际编程过程中，我们常常会为了函数回调而是用apply或call调用。
