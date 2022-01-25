---
title: vue语法入门
date: 2021-12-22
tags: vue
categories: vue
top_img: false
cover: https://xinlong-1305839380.cos.ap-beijing.myqcloud.com/%E5%BC%A0%E9%91%AB%E9%BE%99%E7%9A%84%E5%9B%BE%E7%89%87/%E5%B0%81%E9%9D%A2%E5%B0%8F/3.jpeg
aside: false
swiper_index: 9
swiper_desc: Vue语法
swiper_cover:
---
# Vue语法






<!-- `项目中用的较多的`

* 渲染元素
* 组件（函数组件、类组件）
* 事件处理
* 条件渲染


`首先定义一个React的组件分为函数组件和类组件`

类组件
------
```
import React, { Component } from "react";

export class index extends Component {
  state = {
    list: "这是state里的一个数据",
    listArray: [
      { name: "react", id: 1 },
      { name: "vue", id: 2 },
      { name: "angular", id: 3 },
    ],
  };
  render() {
    const { list, listArray } = this.state;
    return (
      <>
        <div>{list}</div>
        <ul>
          {listArray.map((v: any) => (
            <li>{v.name}</li>
          ))}
        </ul>
      </>
    );
  }
}

export default index;
```

`渲染元素的话 类组件首先找到state里面的值 在render的时候能渲染到页面`

`单个字符串直接就渲染了 如果是数组的话要通过map遍历 `

`结果如下:`

![](/images/渲染元素组件.png)



函数组件
------
```
import React from 'react';

function index() {
  return <div>函数组组件</div>;
}

export default index;
```

条件渲染
------

`条件渲染一般用三元运算符:`

```
import React, { Component } from "react";

export class index extends Component {
  state = {
    flag: true,
    listArray: [
      { name: "react", id: 1 },
      { name: "vue", id: 2 },
      { name: "angular", id: 3 },
    ],
  };
  render() {
    const { flag, listArray } = this.state;
    return (
      <>
        {flag ? (
          <ul>
            {listArray.map((v: any) => (
              <li>{v.name}</li>
            ))}
          </ul>
        ) : (
          "没有渲染任何东西"
        )}
      </>
    );
  }
}

export default index;

```


`上面代码的flag状态如果是true的话就会走数组遍历否则就走没有渲染任何东西`
`结果如下:`
![](/images/三元运算.png) -->
