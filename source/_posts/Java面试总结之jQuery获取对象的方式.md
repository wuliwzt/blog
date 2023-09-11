---
layout: post
title: jQuery获取对象的方式
category: java
date: 2016-09-09 22:36:14
tag: [java]
---
今天面试java工程师，面试题关于io流，javaScript,JDBC连接oracle,struts2等内容。
接着面试官技术面试：
## 1. jQuery获取对象的方式有那些？
1、JQuery的核心的一些方法 
* each(callback) '就像循环 
* $("Element").length; ‘元素的个数，是个属性 
* $("Element").size(); ’也是元素的个数，不过带括号是个方法 
* $("Element").get(); ‘某个元素在页面中的集合，以数组的形式存储 
* $("Element").get(index); ’功能和上面的相同，index表示第几个元素，数组的下标 
* $("Element").get().reverse(); ‘把得到的数组方向 
* $("Element1").index($("Element2")); ’元素2在元素1中的索引值是。。。 
<!--more-->
2、基本对象获取(注意这里获取的都是Jquery对象而不是Dom对象哦，但是他俩是可以转换滴) 
- $("*")  ‘表示获取所有对象   但是我至今没这样用过 
- $("#XXX") ’获得 id=XXX 的元素对象（id可以是标签的id或CSS样式id） 常用 

- $("input[name='username']")   获得input标签中name='userName'的元素对象 常用 

- $(".abc") ' 获得样式class的名字是.abc的元素对象  常用 
- $("div") ' 标签选择器 选择所有的div元素  常用 
- $("#a,.b,span") '表示获得ID是a的元素和使用了类样式b的元素以及所有的span元素 
- $("#a .b p") 'ID号是a的并且使用了 b样式的 所有的p元素

3、层级元素获取 
* $("Element1 Element2 Element3 ....")  '前面父级 后面是子集 
* $("div > p") '获取div下面的所有的 p元素 
* $("div + p") 'div元素后面的第一个 p元素 
* $("div ~ p") 'div后面的所有的 p元素 

4、简单对象获取 
* $("Element:first") 'HTML页面中某类元素的第一个元素 
* $("Element:last") 'HTML页面中某类元素的最后一个元素 
* $("Element:not(selector)") '去除所有与给定选择器匹配的元素,如：$("input:not(:checked)") 表示选择所有没有选中的复选框 
* $("Element:even") '获得偶数行 
* $("Element:odd“）'获得奇数行 
* $("Element:eq(index)")  '取得一个给定的索引值 
* $("Element:gt(index)")  '取得给定索引值的元素  之后的所有元素 
* $("Element:lt(index)")  '取得给定索引值的元素  之前的所有元素 
。。。 

5、内容对象的获取和对象可见性 
* $("Element:contains(text)") '元素中是否包含text文本内容 
* $('Element:empty") '获得元素不包含子元素或文本的 
* $("Element:partnt") '获得元素包含子元素或文本的 
* $("Element:has(selector)") ‘是否包含某个元素， 如：$("p:has(span)")表示所有包含span元素的p元素 
* $("Element:hidden") '选择所有可见元素 
* $("Element:visible") '选择所有不可见元素 

6、其他对象获取方法 
* $("Element[id]") '所有带有ID属性的元素 
* $("Element[attribute = youlika ]" '获得所有某个属性为youlika的元素 
* $("Element[attribute != youlika ]" '获得所有某个属性为不是youlika的元素 
* $("Element[attribute ^= youlika ]" '获得所有某个属性为不是youlika的开头的元素 
* $("Element[attribute $= youlika ]" '获得所有某个属性为不是youlika的结尾的元素 
* $("Element[attribute *= youlika ]" '获得所有某个属性包含youlika的开头的元素 
* $("Element[selector1][selector2][....]") ’符合属性选择器，比如$("input[id][name][value=youlika ]")表示获得带有ID、Name以及value是youlika 的input元素。

7、子元素的获取 
* $("Element:nth-child(index)") '选择父级下面的第n个元素 
* $("Element:nth-child(even)") '选择父级下面的偶数 
* $("Element:nth-child(odd)") '选择父级下面的奇数 
* $("Element:nth-child(3n+1)") '表达式 
* $("Element:first-child") '选择父级下面的第一个子元素 
* $("Element:last-child") '选择父级下面的最后一个子元素 
* $("Element:only-child") '匹配父级下的唯一的一个子级元素，例如dt在dl列表中唯一，那么将选择dt 

8、表单对象获取 
* $(:input)//查找所有的Input元素，当然也包括下拉列表，文本域，单选框，复选框等。 
* $(:text)//匹配所有的单行文本框 
* $(:password)//匹配所有的密码框 
* $(:radio)//匹配所有的单选按钮 
* $(:checkbox)//匹配所有的复选框 
* $(:submit)//匹配所有的提交按钮 
* $(:image)//匹配所有的图像域，例如<input type="image" /> 
* $(:reset)//匹配所有的重置按钮 
* $(:button)//匹配所有的按钮 
* $(:file)//匹配所有的文件上传域 
*  $(:hidden)//匹配所有的不可见元素或者type为hidden的元素 
* $(:enabled)//匹配所有可用的input元素，比如radio:enabled表示匹配所有可用的单选按钮 
* $(:disabled)//匹配所有的不可用input元素，作用与上相反 
* $(:checked)//匹配所有选中的复选框元素 
* $(:selected)//匹配所有的下拉列表 

9、元素属性的设置与移除 
* $("Element").attr(name) '取得第一个匹配的属性值，比如$("img").attr("src") 
* $("Element".attr(key,value)") '某一个元素设置属性 
* $("Element".attr({key:value,key1:value,....})) ‘为某个元素一次性设置多个属性 
* $("Element").attr(key,function) '为所有匹配的元素设置一个计算的属性值。 
* $("Element").removeAttr(name)//移除某一个属性 
