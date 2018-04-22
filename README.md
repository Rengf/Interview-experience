# Interview-experience
面试
2018-04-19<br/>
    今天第一次收到面试邀请，有点小激动，也有点紧张加上对知识点的不熟悉，所以答的不好<br/><br/>
    面试官是一个很好的小哥哥，说话也好听，不懂的他还给我一一解释了<br/>
## CSS<br/>
#### 1.为啥要重置样式表<br/>
--------
    为了重置浏览器的默认样式，统一定义以生成相同的显示效果。<br/>
#### 2.css圆怎么设置<br/>
--------
    利用CSS3,中的border-radius，把值设置为50%即可（我回答设置为100%或50%，他说100%好像不行，<br/>
    我就没回答了（我都是设置的（100%）。然后我下来查了一下，只要大于50%都行，W3C对于重合曲线有<br/>
    这样的规范：如果两个相邻角的半径和超过了对应的盒子的边的长度，那么浏览器要重新计算保证它们不会重合。所以只是设置圆角就50%最好，做动画100%）<br/>
#### 3.清除浮动有哪些方法<br/>
--------
     clear，overflow：hidden，::after<br/>
#### 4.关于布局，左边定宽，右边自适应应该怎么写<br/>
--------
     方法很多，我回答了右边设置一个定宽，设置浮动以后右边的宽度设置为cal(100vw-左边的宽度）,左边左浮动，右边宽度设置为100%；（然后他又问还有其他的没有，我说一时想不起，他就叫我不要紧张，还给我说有一个flex布局，我又想起了），flex布局，设置父容器为display：;然后把右边盒子设置flex:1；<br/>
#### 5.上面的问完以后又问知不知道双飞翼布局；<br/>
--------
    太紧张，没想起怎么写，就说知道这个布局，但是不知道怎么写了（再次叫我不要紧张），说下去好好看一下，然后就进入了js。这应该是css的最后一个问题。
    所谓双飞翼三列布局，中间宽度自适应，两边定宽； 2、中间栏要在浏览器中优先展示渲染。<br/>
        <div class="grid"><br/>
                    <div id="div-middle"><span>div-middle</span></div><br/>
                    <div id="div-left"><span>div-left</span></div><br/>
                    <div id="div-right"><span>div-right</span></div><br/>
                </div><br/>
        样式<br/>
        #div-middle {<br/>
            float: left;<br/>
            background-color:greenyellow;<br/>
            width: 100%;<br/>
            height: 50px;<br/>
        }<br/>
        <br/>
        #div-left{<br/>
            float: left;<br/>
            background-color: rosybrown;<br/>
            width: 200px;<br/>
            margin-left: -100%;<br/>
            height: 50px;<br/>

        }<br/><br/>
        #div-right{<br/>
            float: left;<br/>
            background-color: lightskyblue;<br/>
            width: 200px;<br/>
            margin-left: -200px;<br/>
            height: 50px;<br/>
        }<br/>
            再修改一下“div-middle”属性，放弃两边被覆盖的部分，就能很好地的到需要的效果，可以在“div-middle” <br/>
            里包含一个子div元素，设置margin属性让内容显示在我们的视觉区内，代码如下： <br/>
        CSS代码：<br/>

        #div-wrap{<br/>
                    margin: 0 200px 0 150px;<br/>
                }<br/>
        在div-middle中再加一个div-warp就行：<br/>
#### 6.CSS中有哪些选择器
----
    id class 标签，还有css3中的各种选择器，伪类选择器；然后又问了选择器的优先级id>class>标签，<br/>
    内嵌>内联>外联，设置了@important的优先级最高
#### 7.三角形的实现，
---
    设置border的宽度，然后设置border-color,隐藏三个方向，只给一个方向保留颜色
 
### 关于css问的大概就这些，还有的想起来补上


## JS<br/>
#### 1.怎么让一个字符串顺序颠倒<br/>
---
    var str = '123';<br/>
    var newStr = str.split("").reverse().join("");<br/>
    alert(newStr);<br/>
#### 2.数组的深拷贝<br/>
---
    没想起啥叫深拷贝，就回答了不知道，然后面试官给我我说了深拷贝的一种方法，用循环<br/>
    for 循环实现数组的深拷贝<br/>
    （1）for循环是非常好用的。如果不知道高级方法，通过for循环能够完成我们大多数的需求。<br/>

    var arr = [1,2,3,4,5]<br/>
    var arr2 = copyArr(arr)<br/><br/><br/><br/><br/><br/><br/><br/>
    function copyArr(arr) {<br/><br/><br/><br/><br/><br/><br/>
        let res = []<br/><br/><br/><br/><br/><br/>
        for (let i = 0; i < arr.length; i++) {<br/><br/><br/><br/><br/>
         res.push(arr[i])<br/><br/><br/><br/>
        }<br/><br/><br/>
        return res<br/><br/>
    }<br/>
    （2）slice 方法实现数组的深拷贝<br/>
    这个代码实现非常简单。原理也比较好理解，他是将原数组中抽离部分出来形成一个新数组。<br/>
    我们只要设置为抽离全部，即可完成数组的深拷贝。代码如下：<br/>

    var arr = [1,2,3,4,5]<br/><br/>
    var arr2 = arr.slice(0)<br/>
    arr[2] = 5<br/>
    console.log(arr)<br/>
    console.log(arr2)<br/>
    （3）这个代码也非常简单，原理更加粗暴。它是用于连接多个数组组成一个新的数组的方法。那么，<br/>
    我们只要连接它自己，即可完成数组的深拷贝。代码如下：<br/>

    var arr = [1,2,3,4,5]<br/>
    var arr2 = arr.concat()<br/>
    arr[2] = 5<br/>
    console.log(arr)<br/>
    console.log(arr2)<br/>
    （4）ES6扩展运算符实现数组的深拷贝<br/>
    var arr = [1,2,3,4,5]<br/>
    var [ ...arr2 ] = arr<br/>
    arr[2] = 5<br/>
    console.log(arr)<br/>
    console.log(arr2)<br/>
