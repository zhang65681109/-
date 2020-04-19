#                                       总结

​    2022.3.2

​                   学习了版心的概念。(即用户的浏览器屏幕大小不同,所以将主要的内容都放在版心里面,宽度一般在1000到1400之间就是整个网页分块是个盒子，然后又在这个盒子里面他在套一个盒子。主要内容都在这个套的盒子里面。)然后又学习的图片与文字的一种排列方法(并排的时候) 图片加上 `padding-left`这种模式。然后学习。了这个属性`cusor:pointer`放上去变成手形状。然后又学习了激活位的概念`.类名.active {}`当前元素处于激活状态。然后又大概了解一下，做项目时文件的摆放。

​    2022.3.3-20223.4

​                     这两天尝试做了学校官网的首页。怎么说呢，有一个很大的感触。就是想方设法把这个盒子想方设法的放在正确的位置上。然后再设置样式。而且这两天感觉也认识到不足很多属性都不熟悉。希望能以后能尽早熟悉。还有一定要注意盒子的宽高还有浮动定位的影响什么的，不然可能就布局错乱什么的。

2022.3.5

​                今天学习了markdown跟html差不多吧，也是一种标记语言。不过说实话，代码并不太熟悉都是用tp快捷键写的。然后又学习了form表单。``` html   <inpt type="text  password   radio  checked  submit  file   rest button img  >  <select></select> ,<textarea><texrarea>  laber 标签 fieldset元素集  ```

等等  然后讲了name跟value的用处。然后又学习了一些h5新增的input类型。email  search  url  color{调色盘}

number {属性min  max  step 步长 value} range {范围 } date  week  month  tel {只有在移动端生效}    html <label> xxx <input list="xxx" name+""></label> <datalist id="">  <option  value=">...   </datelist>  .

mater :双标签表示关规定范围内的数量。属性有value  mix  max  low  high .

progress:双标签表示显进度条这个样子。然后又学习了一些表单属性。

multiple能输入多个值。 required必填项目。 novalidate 给form用 关闭验证  formaction上传的不同地址。tabindex获取焦点的顺序。

还讲了bfc {快格式化上下文}主要的意思就是创造了一个封闭的环境，外面影响不到里面里面影响不到外面。 根元素float postion display inline-block  overflow:hiddle  触发快格式化上下文。能解决盒子margin的重叠问题。还有自适应布局。

2022.3.6

​				讲了一些HTML的新增布局标签(表语意化) 然后又讲了媒体标签，音频标签，audio，视频标签video，

然后讲了怎么支持各种浏览器<audio><source src   .mp3   > .....wan  ...ogg   

然后讲了标签语义化能够直观的认识标签和属性的用途和作用，页面的结构把结构更清晰，便于不同的屏幕设备解析，有利于SEO搜索引擎建立良好的关系，有助于爬虫更好的叫信息。便于团队的开发和维护。然后讲了一些新增的选择器子代选择器>兄弟选择器+属性选择器[]   

伪类选择器 :link 链接未被访问。 :visited 链接访问后，  :active 链接被激活的一瞬间。

目标伪类 :target  瞄点  表单伪类。 input:focus  :checked

结构伪类。:nth-child  找的是父亲  确定元素的父亲加自己的子元素。:nth-child (n)盒子里的元素最好一样能生效的你写的那类名    伪元素都是行内元素宽高无效。
xx::after   xx::before  

{ content:"}这个属性必须要加。

::first-letter   ::first-line   ::selection (被选中的文本)

然后又讲了一些web字体，
@font-face {

​						font-family :起名字

​						src:url()

}

还说了怎样使用图标字体参考阿里巴巴的矢量图库。

倒影  {

-webkit-box-reflect :below  r/l  above   或者  below 20px   (距离) linear-gradient :(transpartent-white)

}

然后又讲了盒子模型。

css给盒子设计的宽高仅仅是内容区 的话语加上 padding border    

css3设置了宽高是盒子的页面中实际所占的宽高。如果你增加padding和border，合子所占空间不改变挤占盒子内容  box -sizing :border-box  从普通盒子变成c3盒子。 content-box是css盒子







​                                        