# Interview-experience
面试
2018-04-19
今天第一次收到面试邀请，有点小激动，也有点紧张加上对知识点的不熟悉，所以答的不好
面试官是一个很好的小哥哥，说话也好听，不懂的他还给我一一解释了
##CSS
#1.为啥要重置样式表
为了重置浏览器的默认样式，统一定义以生成相同的显示效果。
#2.css圆怎么设置
利用CSS3,中的border-radius，把值设置为50%即可（我回答设置为100%或50%，他说100%好像不行，我就没回答了（我都是设置的（100%）。然后我下来查了一下，只要大于50%都行，W3C对于重合曲线有这样的规范：如果两个相邻角的半径和超过了对应的盒子的边的长度，那么浏览器要重新计算保证它们不会重合。所以只是设置圆角就50%最好，做动画100%）
#3清除浮动有哪些方法
clear，overflow：hidden，::after
#4关于布局，左边定宽，右边自适应应该怎么写
方法很多，我回答了右边设置一个定宽，设置浮动以后右边的宽度设置为cal(100vw-左边的宽度）,左边左浮动，右边宽度设置为100%；（然后他又问还有其他的没有，我说一时想不起，他就叫我不要紧张，还给我说有一个flex布局，我又想起了），flex布局，设置父容器为display：;然后把右边盒子设置flex:1；
#5.上面的问完以后又问知不知道双飞翼布局；
太紧张，没想起怎么写，就说知道这个布局，但是不知道怎么写了（再次叫我不要紧张），说下去好好看一下，然后就进入了js。这应该是css的最后一个问题。
所谓双飞翼三列布局，中间宽度自适应，两边定宽； 2、中间栏要在浏览器中优先展示渲染。
<div class="grid">
            <div id="div-middle"><span>div-middle</span></div>
            <div id="div-left"><span>div-left</span></div>
            <div id="div-right"><span>div-right</span></div>
        </div>
样式
#div-middle {
    float: left;
    background-color:greenyellow;
    width: 100%;
    height: 50px;
}

#div-left{
    float: left;
    background-color: rosybrown;
    width: 200px;
    margin-left: -100%;
    height: 50px;

}
#div-right{
    float: left;
    background-color: lightskyblue;
    width: 200px;
    margin-left: -200px;
    height: 50px;
}
再修改一下“div-middle”属性，放弃两边被覆盖的部分，就能很好地的到需要的效果，可以在“div-middle” 
里包含一个子div元素，设置margin属性让内容显示在我们的视觉区内，代码如下： 
CSS代码：

#div-wrap{
            margin: 0 200px 0 150px;
        }
1
2
3
body里的代码：

<div id="div-middle">
    **<div id="div-wrap"><span>div-middle</span></div>**
</div>







