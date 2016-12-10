---
title: Hello Word
date: 2016-08-13 10:00:22
tags:
---

### 测试标签页面（Tag Plugins）
 {% blockquote %}  
orem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque hendrerit lacus ut purus iaculis feugiat. Sed nec tempor elit, quis aliquam neque. Curabitur sed diam eget dolor fermentum semper at eu lorem.
 {% endblockquote %}

{% blockquote David Levithan, Wide Awake %}  
    Do not just seek happiness for yourself. Seek happiness for all. Through kindness. Through mercy.  
{% endblockquote %} 


<!--more -->

### 引用网络上的文章

{% blockquote Seth Godin  http://blog.jobbole.com/86614/%}  
Every interaction is both precious and an opportunity to delight.  
{% endblockquote %}  


### 代码引用（Code Block）
{% codeblock [title] [lang:language] [url] [link text] %}  
code snippet  
{% endcodeblock %}  



{% codeblock %}
alert('Hello World!');
{% endcodeblock %}


{% codeblock lang:php %}  
public function test(){
        $user = I('post.username');
        $pwd = I('post.passwd');
        if(!empty($user)||$pwd){
            echo '用户名不能为空';
        }
        
}   
{% endcodeblock %}  


{% codeblock _.compact http://underscorejs.org/ %}  
    _.compact([0, 1, false, 2, '', 3]);  
    => [1, 2, 3]  
{% endcodeblock %}  


### Pull Quote
<!--10-->

{% pullquote [class] %}  
    content  
{% endpullquote %} 




{% iframe http://blog.jobbole.com/86614/ [100%] [600] %}

 {% img [class names] /path/to/image [width] [height] [title text [alt text]] %} 

















