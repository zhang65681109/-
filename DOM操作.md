# 	         	DOM操作

  DOM:文档对象模型，操作网页上的元素的 API。比如让盒子移动、变色、轮播图等。

 HTML中的一切都是节点可分成

1. 元素节点  HTML标签
2. 文本节点  标签中的文字
3. 属性节点   标签的属性 

每个节点都是对象  通过操作节点来得到我们想要的结果.



事件的三要素：事件源、事件、事件驱动程序

事件源   谁引发的后续事件，谁就是事件源

事件        事情的发生需要的一些动作

事件驱动程序   结果 

事件有

onabort      图像加载被中断

onblur         元素失去焦点

onchange    用户改变域的内容

onclick         鼠标点击某个对象

ondblclick    鼠标双击某个对象

onerror         当加载文档或图像时发生某个错误

onfocus        元素获得焦点

onkeydown    某个键盘的键被按下

onkeypress    某个键盘的键被按下或按住

onkeyup        某个键盘的键被松开

onload           某个页面或图像被完成加载

onmousedown  某个鼠标按键被按下

onmousemove  鼠标被移动

onmouseout     鼠标从某元素移开

onmouseover    鼠标被移到某元素之上

onmouseup     某个鼠标按键被松开

onreset             重置按钮被点击

onresize           窗口或框架被调整尺寸

onselect           文本被选定

onsubmit          提交按钮被点击

onunload          用户退出页面

等等



操作流程 

```js
var div1 = document.getElementById("box1"); //方式一：通过id获取单个标签
var arr1 = document.getElementsByTagName("div"); //方式二：通过 标签名 获得 标签数组
var arr2 = document.getElementsByClassName("hehe"); //方式三：通过 类名 获得 标签数组



绑定事件
div1.onclick = function() {
   //处理程序   div1.style.backgroundColor = "red";
}

//class名 标签名  同原理  不过因为是伪数组  注意下标.



//获取下一个兄弟节点
 var nextEl = pEl.nextElementSibling || pEl.nextSibling;


//获取父元素
var pNode = pEl.parentNode;
//第一个子元素
var first = pNode.firstElementChild || pNode.firstChild;
// 最后一个子元素
  var last = pNode.lastElementChild || pNode.lastChild;
//  所有的子元素 节点
   var lis = 父元素.children;  //获取的是数组
//childNodes 包含 文本.注释.这些节点
// 节点类型  nodeType 
// nodeType: 1  元素  可以通过这个封装一个函数,来兼容。ie678 获取所有子元素。
   function myChildren(el){
            var children = el.childNodes;
            var temp = [];
            for(var i =0;i<children.length;i++){
                if(children[i].nodeType === 1){
                    temp.push(children[i])
                }
            }
            return temp;
        }

        // 获取自己后边的所有 兄弟元素
        // 锁的思想
        function nextSiblings(el){
            var pNode = el.parentNode;
            var children = pNode.children; 
            var temp = [];
            var lock = true;
            for (var i = 0; i < children.length; i++) {
                if(children[i]===el){
                    lock = false;
                    continue;
                if(lock){
                }else{
                    temp.push(children[i]);
                }
            }
            return temp;
            
        }
            
    //节点的增删改查
     var pEl = document.createElement('p');
    //创建了一个p标签
     父元素.appendChild(pEl); 
            //类似于 数组的push  这个父元素的最后一个标签.
     // 父节点.insertBefore(新的子节点, 作为参考的子节点);
     // 指定 插入到 哪个子元素的前边
     box.insertBefore(img1,p2); 	
    //把img1插到p2的前面
    //删除节点
    父节点.removeChild(子节点);
    var clone = img.cloneNode();
            // 要复制的节点.cloneNode();括号里不带参数和带参数false，效果是一样的。 要复制的节点.cloneNode(true);
        // 不带参数/带参数 false：只复制节点本身，不复制子节点。
        // 带参数 true：既复制节点本身，也复制其所有的子节点。
          box .getAttribute('')  获取属性
       box .setAttribute('','')  设置属性
        box.removeAttribute('')  删除属性
        
        box.classList.toggle('active'); //切换类名
        box.classList.remove('active');//删除类名
        box.classList.add('active');  //增加类名
        box.classList.contains('active')//查看这个类名有没有存在



```



获取dom 元素的新方法

var box = document.querySelector('.box');  单个类名

var lis = document.querySelectorAll('.item') 有相同的类名 也是数组



```js
<li data-bck="yellow">5</li>
        var lis = document.querySelectorAll('li');
        for (var i = 0; i < lis.length; i++) {
            var bck = lis[i].dataset['bck'];
            lis[i].style.backgroundColor = bck;
        }
        //data
//通过data - xxx自定义一个属性   然后通过 .dataset['xxx']获取这个.


        function jf(x,y){
            console.log(arguments);//要在函数执行之前 只能在函数里面
            console.log(arguments.callee);//函数自己
            return x+y
       
        }
        console.log(jf(3,5));
     //arguments 保存了 传进来的 实参信息




	 window.onload = function(){
         xxxxx
     }
//整个页面加载完执行的函数  

 
 
```





事件监听器  绑定事件的另外一种方法  可以绑定多个事件

 innerbox.addEventListener('click',function(){

​      console.log('inner1');

​    }false)

​    innerbox.addEventListener('click',function(){

​      console.log('inner2');

​    },false)

即innerbox 绑定了2个点击事件 打印1 和打印2    在冒泡阶段

```js 
       div.addEventListener('click',cos,false);
        btn.onclick = function(){
            div.removeEventListener('click',cos,false);  //不能加括号  一一对应
        }
      

       function cos(){
            console.log('div')
        }  
    //移除时 需要外部函数  
```





定时器

```js
 var ad = document.querySelector('.ad');
        var stime = setTimeout(function () {
            ad.style.display = 'none'
        }, 3000);    //延迟


        //循环
        var set = setInterval(function () {
            console.log('2')
        }, 1000);
        var btn1 = document.querySelector('.btn1');
        var btn2 = document.querySelector('.btn2')
        //移除
        btn1.onclick = function () {
            clearTimeout(stime);
        };
        btn2.onclick = function () {
            clearInterval(set);
        }
        
        // 如何移除定时器 循环定时器开启了 ,怎么关闭呢
        // clearInterval 移除循环定时器
        // clearTimeout   移除延迟定时器
        // 移除时  需要给定时器 起名字
```





闭包  在函数外部用到了函数内部的变量

```js
var a = 10;
        function say(){
             x =1
            return function(){
                console.log(x);
            }
        }
        var a = say()
        console.log(a)
        a()
        console.log(x)//1

//通过这个就可以等到索引
//立即执行函数
for(var i = 0;i<lis.length;i++){
            lis[i].onclick = (function(n){
                return function(){
                    console.log(n);
                }
            }(i))
        }

  var div = document.querySelector('div')

        var a =window. getComputedStyle(div,null).getPropertyValue('background-color');
        console.log(a)

//可以通过这个获取样式表的属性  不支持驼峰命名
```

