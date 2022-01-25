---
title: css溢出显示省略号
date: 2021-12-12
tags: css
categories: css
top_img: false
cover: https://xinlong-1305839380.cos.ap-beijing.myqcloud.com/%E5%BC%A0%E9%91%AB%E9%BE%99%E7%9A%84%E5%9B%BE%E7%89%87/%E5%B0%81%E9%9D%A2%E5%B0%8F/1.jpeg
aside: false
swiper_index: 10
swiper_desc: CSS实现单行、多行文本溢出显示省略号（…）
swiper_cover: https://xinlong-1305839380.cos.ap-beijing.myqcloud.com/%E5%BC%A0%E9%91%AB%E9%BE%99%E7%9A%84%E5%9B%BE%E7%89%87/%E5%B0%81%E9%9D%A2%E5%B0%8F/1.jpeg
---
# CSS实现单行、多行文本溢出显示省略号（…）

**项目中常常有这种需要我们对溢出文本进行"..."显示的操作，单行多行的情况都有（具体几行得看设计师心情了），这篇随笔是我个人对这种情况解决办法的归纳，欢迎各路大佬指教。**

```
    <div class="hideBox">
      如果实现单行文本的溢出显示省略号同学们应该都知道用text-overflow:ellipsis属性来，当然还需要加宽度width属来兼容部分浏览
    </div>
```

单行
------

```
    .hideBox {
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
        max-width: 200px;
      }
```
`效果如下:`
![](/images/溢出省略号单行.png)

这个属性只支持单行文本的溢出显示省略号，并且要限制宽度，如果我们要实现多行文本溢出显示省略号呢。接下来重点说一说多行文本溢出显示省略号，如下:

多行
------

```
    .hideBox {
        overflow: hidden;
        text-overflow: ellipsis;
        display: -webkit-box;
        -webkit-line-clamp: 2;//这是两行超出溢出...是几行溢出就改成几
        -webkit-box-orient: vertical;
      }
```

`效果如下:`
![](/images/溢出省略号多行.png)

``移动端浏览器绝大部分是WebKit内核的，所以该方法适用于移动端，自适应宽度显示省略号``

* -webkit-line-clamp 用来限制在一个块元素显示的文本的行数,这是一个不规范的属性（unsupported WebKit property），它没有出现在 CSS 规范草案中。
* display: -webkit-box 将对象作为弹性伸缩盒子模型显示 。
+ -webkit-box-orient 设置或检索伸缩盒对象的子元素的排列方式 。
* text-overflow: ellipsis 以用来多行文本的情况下，用省略号“…”隐藏超出范围的文本。









