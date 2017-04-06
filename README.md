# 在 Liferay 的网页内容中使用 AlloyUI

关于AlloyUI，[AlloyUI](http://alloyui.com/) 官网的介绍如下：
> AlloyUI 是构建在 Yahoo 的 YUI3（JavaScript）之上的框架，使用 Bootstrap（HTML/CSS）为构建高度可伸缩的应用程序提供一个简单的API。 

简而言之，AlloyUI 是由 Liferay 团队基于 YUI 和 Bootstrap 开发的前端 UI 框架，在 Liferay Portal 6.2.x 中被广泛使用。虽然 Yahoo 已经不在积极维护 YUI 了，而且 Liferay 团队也决定不在为 AlloyUI 开发新的组件，但是在最新的 Liferay Portal CE 7.0.x 中还是默认集成了 AlloyUI，并且还是会积极维护 AlloyUI。

正是由于在 Liferay Portal 中默认集成了AlloyUI，因此我们使用起来也非常地简单，接下来我们会在 Liferay Portal CE 7.0.2（其他版本也可以参照实现）中实现一个简单的轮播图（[官网示例](http://alloyui.com/examples/carousel/real-world/)），来展示如何在网页内容中使用 AlloyUI。

1. 启动Liferay Portal，使用超级管理员账户登录，访问任意的页面，这里以 Welcome 页面为例
1. 首先单击右上角的 *+* 按钮，然后选择”内容“面板，选择”添加新的“》”基本网页内容“，打开”新的网页内容“界面
1. 在标题输入框中输入“在 Liferay 的网页内容中使用 AlloyUI”
1. 在内容输入框中切换到源代码视图（点击右上角的</>图标）,复制以下官方示例代码：
```
<div id="myCarousel">
  <div class="image-viewer-base-image" style="background: url(http://alloyui.com/carousel/img/1.jpg);"></div>
  <div class="image-viewer-base-image" style="background: url(http://alloyui.com/carousel/img/2.jpg);"></div>
  <div class="image-viewer-base-image" style="background: url(http://alloyui.com/carousel/img/3.jpg);"></div>
  <div class="image-viewer-base-image" style="background: url(http://alloyui.com/carousel/img/4.jpg);"></div>
</div>
<script>
	YUI().use(
	  'aui-carousel',
	  function(Y) {
	    new Y.Carousel(
	      {
	        activeIndex: 'rand',
	        contentBox: '#myCarousel',
	        height: 250,
	        intervalTime: 2,
	        width: 700
	      }
	    ).render();
	  }
	);
</script>
```
1. 然后点击“保存”按钮，在页面上就可以看到轮播图的实现。

> 注意：以上步骤并不需要引入任何额外的 js 或者 css 文件，因为这些 Liferay Portal 默认的主题已经集成了。

