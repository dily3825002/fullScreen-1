# 某个元素的全屏与退出全屏的功能
fdsfdsfd
效果如下：
![](img.gif)

demo code:
```
<!DOCTYPE html>
<html>
    <head>
        <meta http-equiv="Content-Type" content="text/html; charset=gb2312">
        <title></title>
        <style type="text/css">
            .div1{
                width: 1000px;height: 500px;
                border: solid 1px blue;
            }
            .test{        
                width:100%;        
                background: black;
                height:100%;
                min-height: 400px;
                border: solid 1px red;                
            }
            div{
                color: #fff;
            }
        </style>
        
    </head>
    <body>
		<!-- 如果你想兼容一些低版本的ie浏览器，你可以替换我做提示的区域

		alert("当前浏览器不支持全屏化操作！");
		让你想全屏的部分，width:100%;height:100%;
		然后再让他的父类节点的高度和宽度等于当前可用浏览器的最大宽度和高度就行啦。
		在这里没有做具体的实现。
		本人，不是很建议去兼容低ie浏览器，因为做前端的都知道，现在大部分html5和css3,ES6都不在积极的淘汰
		低版本浏览器。微软也放弃了对低版本ie浏览器的维护。-->
        <div class="div1" >
            <div id="div2"  class="test">
                <div id="div" class="" style="border:solid 1px #ffffff;width:100px;height:40px;">全屏</div>
                <div id="div3" class="" style="border:solid 1px #ffffff;width:100px;height:40px;">取消全屏</div>
            </div>
        </div>
        
        
        <script>
            (function () {
                var viewFullScreen = document.getElementById("div");    
                if (viewFullScreen) {
                    viewFullScreen.addEventListener("click", function () {
                        var docElm = document.getElementById("div2");
                        if (docElm.requestFullscreen) {
                            docElm.requestFullscreen();
                        }
                        else if (docElm.msRequestFullscreen) {
                            docElm.msRequestFullscreen();
                        }
                        else if (docElm.mozRequestFullScreen) {
                            docElm.mozRequestFullScreen();
                        }
                        else if (docElm.webkitRequestFullScreen) {
                            docElm.webkitRequestFullScreen();
                        }else{
                            alert("当前浏览器不支持全屏化操作！");
                        }
                    }, false);
                }
            
                var cancelFullScreen = document.getElementById("div3");
                if (cancelFullScreen) {
                    cancelFullScreen.addEventListener("click", function () {
                        if (document.exitFullscreen) {
                            document.exitFullscreen();
                        }
                        else if (document.msExitFullscreen) {
                            document.msExitFullscreen();
                        }
                        else if (document.mozCancelFullScreen) {
                            document.mozCancelFullScreen();
                        }
                        else if (document.webkitCancelFullScreen) {
                            document.webkitCancelFullScreen();
                        } else{
                            alert("当前浏览器不支持全屏化操作！");
                        }
                    }, false);
                }                        
            })();
			
			


        </script>
    </body>
</html>
```
