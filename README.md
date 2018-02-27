<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title></title>
    <style>
        *{margin: 0; padding: 0;}
        ul {list-style:none;}
        body {
            background-color: #000;
        }
        .nav {
            width: 800px;
            height: 42px;
            background:url("images/rss.png") no-repeat right center #fff;
            margin: 100px auto;
            border-radius: 5px;
            position: relative; 
        }
        .cloud {
            width: 83px;
            height: 42px;
            position: absolute;
            top: 0;
            left: 0;
            background: url(images/cloud.gif) no-repeat;
        }
        .nav ul {
            position: absolute;
            top: 0;
            left: 0;
        }
        .nav li {
            float: left;
            width: 83px;
            height: 42px;
            line-height: 42px;
            text-align: center;
            color: #000;
            cursor: pointer;
        }
    </style>
</head>
<body>
<div class="nav" id="nav">
    <span class="cloud" id="cloud"></span>
    <ul>
        <li>首页新闻</li>
        <li>师资力量</li>
        <li>活动策划</li>
        <li>企业文化</li>
        <li>招聘信息</li>
        <li>公司简介</li>
        <li>上海校区</li>
        <li>广州校区</li>
    </ul>
</div>
</body>
</html>
<script>
    var cloud  = document.getElementById("cloud");  // 云彩
    var nav = document.getElementById("nav");
    var lis = nav.children[1].children;
    var current = 0;   // 用于存放点击时候的 offsetLeft
    //alert(lis.length);
    for(var i=0; i<lis.length;i++) {
        lis[i].onmouseover = function() {
            // alert(this.offsetLeft);
            target = this.offsetLeft;  // 把左侧的位置 ，给 target
        }
        lis[i].onmouseout = function() {
            target = current;     // 鼠标离开  target 是 刚才我们点击的位置
        }
        lis[i].onclick = function() {
           current = this.offsetLeft;   //  点击的时候 吧当前位置 存贮一下
        }
    }
    // 缓动公式
    var leader = 0, target = 0;
    setInterval(function(){
        leader = leader + (target - leader ) / 10;
        cloud.style.left = leader + "px";
    },10);
</script>
