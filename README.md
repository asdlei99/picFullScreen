 ```
 <script type="text/javascript">
        function hasClass(obj, cls) {
            return obj.className.match(new RegExp('(\\s|^)' + cls + '(\\s|$)'));
        }
         
        function addClass(obj, cls) {
            if (!this.hasClass(obj, cls)) obj.className += " " + cls;
        }
         
        function removeClass(obj, cls) {
            if (hasClass(obj, cls)) {
                var reg = new RegExp('(\\s|^)' + cls + '(\\s|$)');
                obj.className = obj.className.replace(reg, ' ');
            }
        }


        window.addEventListener('load', function () {
            var imgs = document.getElementsByClassName('post-body')[0].getElementsByTagName('img')
            for(var i=0;i<imgs.length;i++){
                //如果设置非全屏标志则跳过
                if(hasClass(imgs[i],'class_no_full_screen')){
                    continue;
                }
                // imgs[i].setAttribute('data-background', 'rgba(10, 10, 10, .6)');
                // imgs[i].setAttribute('data-lightense-padding', "0");
                imgs[i].setAttribute('style', "cursor: zoom-in");
                imgs[i].onclick=function(){
                
                    var section=document.getElementsByTagName("section")[0];

                    var imgView = document.getElementById('imgViewDom');
                    if(imgView == undefined){
                        imgView=document.createElement("div");
                        imgView.id = "imgViewDom";

                        section.appendChild(imgView)

                        imgView.onclick = function(){
                            addClass(imgView, "disnone");
                            imgView.innerHTML="";
                        }
                    }
            
                    imgView.innerHTML="<img id = 'jackslowfuck' src=" + this.src + " style='cursor: zoom-out; max-width: 100%;'" + ">";
                    removeClass(imgView, "disnone");

                    var jackslowfuck = document.getElementById('jackslowfuck');
                    jackslowfuck.onclick=function(){
                        addClass(imgView, "disnone");
                        imgView.innerHTML="";
                    }

                }
            }
            
        }, false);
    </script>

    <style type="text/css">
        #imgViewDom {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            height: 100%;
            width: 100%;
            z-index: 99999999;
            background: rgba(255, 255, 255,0.8);
            overflow: auto;
            display: -webkit-box;
            -webkit-box-align: center;
            -webkit-box-pack: center;
            display: -moz-box;
            -moz-box-align: center;
            -moz-box-pack: center;
            display: -o-box;
            -o-box-align: center;
            -o-box-pack: center;
            display: -ms-box;
            -ms-box-align: center;
            -ms-box-pack: center;
            display: box;
            box-align: center;
            box-pack: center;
        }

        .disnone{
            display: none !important;
        }
    </style>
```

# picFullScreen
给页面所有的图片加上全屏预览功能

## 食用方法
* 在页面的head部分加入上述代码
* 只需要改变js中的*post-body*  var imgs = document.getElementsByClassName('post-body')[0].getElementsByTagName('img')
* 对不需要展示的图片加上 class_no_full_screen 类
* 如果要修改背景色请修改*background: rgba(255, 255, 255,0.8);*这一句

## 全屏展示页面
[详情页面](https://spygg.github.io/2019/04/21/%E7%BB%99%E9%A1%B5%E9%9D%A2%E6%89%80%E6%9C%89%E7%9A%84%E5%9B%BE%E7%89%87%E5%8A%A0%E4%B8%8A%E5%85%A8%E5%B1%8F%E9%A2%84%E8%A7%88%E5%8A%9F%E8%83%BD/)


## 非全屏参见
[非全屏](https://spygg.github.io/about/)


## ps
我是javasciript的菜鸟,只会这种简单粗暴的方法


