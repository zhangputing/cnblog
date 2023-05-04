# 从头开始

博客园最让人着迷的一点就是可以自定义 DOM 结构，这样就可以很方便的实现一些特殊的需求。
彰显自己的个性，这也是博客园的一大特色。
本文是对定制一个自己的博客园主题的一些记录。

## dom 结构

### 主页的核心 dom 结构如下：

```html
<body>
  <div id="top_nav">
    顶部导航
    <nav id="nav_main">
      <ul id="nav_left"></ul>
      <ul id="nav_right"></ul>
    </nav>
  </div>
  <div id="page_begin_html">页首html</div>
  <div id="home">
    <div id="header">
      <div id="blogTitle"></div>
      <div id="navigator"></div>
    </div>
    <div id="main">
      <div id="mainContent"></div>
      <div id="sideBar"></div>
      <div id="clear"></div>
    </div>
    <div id="footer"></div>
  </div>
  <div id="page_end_html">页尾html</div>
</body>
```

整体的结构还是比较清晰的，同时所有的内容都可以通过 id 来获取到，这样就可以很方便的进行定制。

## 导航栏 dom

```html
<div class="navbar">
  <div class="navbar-item">
    <a href="https://www.cnblogs.com" target="_blank">
      <div class="navbar-item-avatar">
        <div class="icon"></div>
        <div class="text">博客园</div>
      </div>
    </a>
  </div>
  <div class="navbar-item">
    <a href="https://www.cnblogs.com" target="_blank">
      <div class="navbar-item-avatar">
        <div class="icon"></div>
        <div class="text">首页</div>
      </div>
    </a>
  </div>
  <div class="navbar-item">
    <a href="https://www.cnblogs.com" target="_blank">
      <div class="navbar-item-avatar">
        <div class="icon"></div>
        <div class="text">新随笔</div>
      </div>
    </a>
  </div>
  <div class="navbar-item">
    <a href="https://www.cnblogs.com" target="_blank">
      <div class="navbar-item-avatar">
        <div class="icon"></div>
        <div class="text">新博文</div>
      </div>
    </a>
  </div>
  <div class="navbar-item">
    <a href="https://www.cnblogs.com" target="_blank">
      <div class="navbar-item-avatar">
        <div class="icon"></div>
        <div class="text">联系</div>
      </div>
    </a>
  </div>
  <div class="navbar-item">
    <a href="https://www.cnblogs.com" target="_blank">
      <div class="navbar-item-avatar">
        <div class="icon"></div>
        <div class="text">管理</div>
      </div>
    </a>
  </div>
</div>
```

其中#mainContent可以通过重写css将一些margin覆盖掉

```scss
#mainContent {
  margin-left: 0;
  min-height: 200px;
  padding: 0 0 10px 0;
  text-overflow: ellipsis;
  overflow: hidden;
  float: none;
  .forFlow {
    margin-left: 15px;
  }
}
```
