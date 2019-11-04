# VueH5

## 项目介绍

本项目使用的是用vue+vue-cli脚手架，模仿的 “去哪网” 移动端端页面。使用的技术有 vue ， vue-cli , webpack , vuex， stylus, axios, fastclick, vue-awesome-swiper等等。

### 项目预览

[演示地址：https://jonesxie.github.io/demobox/VueH5/](https://jonesxie.github.io/demobox/VueH5/)

>请在手机端，或控制台模拟移动端进行浏览

## 使用的技术,按照使用顺序排列

1. vue-cli脚手架搭建，使用的是webpack打包工具

2. 引入rest.css样式，对css样式进行初始化。

3. 引用border.css，更加方便使用一像素边框

4. 引用stylus插件，使得编写css样式更加简便

5. 使用vue-awesome-swiper插件，对首页中的轮播图使用该插件

![vue-awesome-swiper](https://jonesxie.github.io/VueH5/src/assets/img/intro_index.png "vue-awesome-swiper")

6.使用axios获取数据，此Demo中大部分数据都是通过 axios 插件获取的json格式文件，模拟接入后台文件。

> 1. 首页轮播图地址获取：<https://jonesxie.github.io/VueH5/src/assets/api/index.json>  
>2. 城市列表页获取：<https://jonesxie.github.io/VueH5/src/assets/api/city.json>  
>3. 详情页相关数据获取：<https://jonesxie.github.io/VueH5/src/assets/api/detail.json>  

7.使用better-scroll插件，在城市列表中使用此插件，实现在移动端可以滑动，并出现一些默认触顶动画。联动了右边字母排序，滑动右侧字母表可以实时滚动相对应的字母区域块。

8.使用vuex对数据进行跨组件传输。比如在城市列表页中，选择某一城市后，在首页中城市也将随之改变

9.使用vue-router路由对整个页面和子页面进行调试。

## 体验说明

1.当进入页面时，手机是横屏状态将会提醒：

![横屏提示](https://jonesxie.github.io/VueH5/src/assets/img/horizontal_tip.png "tips")

2.主页详情

![主页详情](https://jonesxie.github.io/VueH5/src/assets/img/intro_index.png "index.png")

3.点击左上角城市页面，进入城市列表页

>1.点击顶部输入框，将会搜索城市  
>2.上下滑动字母表，城市列表也会联动  
>3.随意点击任何一个城市，将返回首页，并更新当前城市

![城市列表](https://jonesxie.github.io/VueH5/src/assets/img/intro_city.png "list.png")

4.点击热销推荐列表，将进入详情页

>1.点击顶部图片，将会进入图片展示页，可以左右滑动
>2.上滑，将会出现顶部蓝色头部导航栏

![热销推荐](https://jonesxie.github.io/VueH5/src/assets/img/intro_detail.png "pic.png")
