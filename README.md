# vue
## 基本概念

### Vue是什么?

```
官网:https://cn.vuejs.org/
Github:https://github.com/vuejs/vue
核心的类库 比较小 min.vue.js min.vue-router.js
注意:
	兼容只兼容IE9及以上
```

### 能做什么?

```
PC:网站，后台管理系统
移动端：webapp、Weex
```

### 如何学习它?

```
学习网站:
	https://cn.vuejs.org/v2/guide/
百度
www.stackoverflow.com
开源的网站:
	https://segmentfault.com/p/1210000008583242/read?from=timeline	
	https://www.awesomes.cn/subject/vue#应用-框架
```

### Hello World

```
MVC 
	M:模型  提供数据 $scope.xxx
	V:视图 html
	C:处理业务逻辑	
MVVM
	好处:
		1、低耦合
		2、重用性高		
注意事项:
	一个项目，一般只能有唯一的一个根实例(创建的Vue对象)
```

### CDN

```
内容分发网络	
```

------

## 指令

```
在页面中先占着位，然后通过数据去替换
```

```
注意:
	vue中所有的指令都是以`v-`开头的
```

### 表达式 `{{}}`

### v-text&v-html

```
v-text 文本
v-html 页面html内容
```

### v-bind

```
v-bind 页面上的数据不是写死的，数据是动态变化的
```

### v-model

```
双向数据绑定
```

```
数据 ---> 视图
	this.result = parseInt(this.v1) + parseInt(this.v2)
视图 ---> 数据
注意事项:
	使用我们vue的调试工具，不要使用压缩版本的vue，否则没有效果
```

### v-on 事件

```
如果我们要执行的函数中没有参数，那么我们在绑定方法的时候，可以加上()，也可以不加
有参数必须得加
v-on:click = "函数"
@click = "函数"
```

### v-if/v-show

```
v-if 如果条件为true  有这个元素
v-if 如果条件为false 没有这个元素

v-show 如果条件为true  有这个元素
v-show 如果条件为false 有这个元素，只是隐藏

实际开发中如何抉择?
	如果你要频繁的切换，用v-show，初始化的时候有性能开销
	
	如果你不是频繁的切换，只需要显示一次，用if 初始化的时候的性能开销小
```

### v-for

```
v-for 遍历的时候，要遍历的是，你需要循环生成的标签
```

```
v-for在循环生成html元素的时候，它是在生成下一行的
时候，会复用上一行的标签，这样因为它们指向都是同一
块内存空间，如果发生更改可能会影响到其他行，我们只
需要给遍历的每一个的html元素，设置一个唯一的标识
符，这可以了，相当于告诉Vue，我生成的下一行的元素
和上面的没有任何关系
给遍历到的每一个元素，添加一个key就行了，但是这个key值必须要是唯一的
注意事项:
	如果遍历的数组的每一项中，数据项有唯一的标识符，可以用唯一标识符和index，如果没有用index即可
```

------

## 组件

```
1、功能代码的集合
	html+css+js
2、呈现在用户面前(页面)
```

### Vue中定义组件的五种方式

```
前四种【了解】
	1、先定义，在注册，然后在使用
		定义:extend
		注册:component
	2、定义注册合成一步，在使用
		见代码	
	3、把组件定义代码写在template之间
		见代码
	4、把组件定义代码写在script之间
```

```
第五种【掌握】:
	单文件组件，三部分 template script style
注意点:
	1、组件里面必须要有一个根元素
	2、第二种是对第一种的一个简化
	3、第3，4中是对我们第二种的优化
	4、组件只有注册之后才能使用
```

------

## 过滤器

```
作用:
	对数据(服务器)返回的数据进行过滤，让其能够满足我们的需求
注意:
	1、vue 1.x中内置的过滤器，vue2.x移除了内置的过滤器，我们必须自己写
	2、过滤器是一个函数，过滤器是写在vm中的filters中的
	3、过滤器处理函数中一定要return
	4、过滤器中的参数，第一个一定是`|`前面的，第二个参数就是调用过滤器传递的
```

### 分类

```
私有过滤器
	定义在Vue实例中，在filters中写

全局过滤器
	Vue.filter(过滤器名称,处理函数)
```

------

## 路由

```
作用:
	根据我们触发的超链接，决定把哪个页面（组件）呈现在浏览器中
网址:
	https://router.vuejs.org/zh-cn/
```

### Vue中路由的几个概念

```
1、触发链接
2、组件
3、设置好路由的规则
4、router-view
```

### Vue中路由的使用

```
思路:
	html中
		1、触发超链接的东西 router-link
		2、router-view
	js中	
		1、定义组件
		2、设置路由规则
		3、把路由注入到根实例中
注意点:
	1、路由的功能没有包含在vue.js中，所以要是用路由，必须引入路由js文件
	2、写代码写两大块，第一块html中如何写，第二块，是在javascript怎么写
```

------

## 网络请求(Ajax)

### vue-resource

```
前提准备：
	1、导入vue.js
	2、导入vue-resource.js
	
正是写代码
	参考:https://github.com/pagekit/vue-resource
GET:
	见代码
POST:
	参考:
		https://github.com/pagekit/vue-resource/blob/develop/docs/http.md	
	别忘记设置请求头 
		{emulateJSON:true}
```

------

## Webpack使用

```
参考:http://zhaoda.net/webpack-handbook/install.html
```

### 打包一个.js文件

```
步骤:
	1、先编写源代码
		新建index.html
		创建entry.js
	2、利用webpack打包
		切换到项目根目录，调用 `webpack 打包的入口文件 输出文件`
	3、在index.html中导入bundle.js
		注意点:不要导入源文件,那你还要webpack干嘛
```

### 打包多个并且有依赖关系的.js文件

```
步骤:
	1、先编写源代码
		新建index.html
		创建entry.js
		创建module.js
	2、利用webpack打包
		切换到项目根目录，调用 `webpack 打包的入口文件 输出文件`
		
	3、在index.html中导入bundle.js
		注意点:不要导入源文件,那你还要webpack干嘛
```

### 打包css文件---loader

```
步骤:
	1、先编写源代码
		新建index.html
		创建entry.js
		创建module.js
		创建site.css
		
	2、利用webpack打包
		切换到项目根目录，调用 `webpack 打包的入口文件 输出文件`
		
	3、在index.html中导入bundle.js
		注意点:不要导入源文件,那你还要webpack干嘛
		
每个文件对应的loader
	参考：
		https://doc.webpack-china.org/loaders/
		
		https://github.com/webpack/webpack
	
会报错:
	You may need an appropriate loader to handle this file type. 打包了非js文件，并且还没有使用loader
	
解决步骤:
	1、先安装 style-loader css-loader
		npm i style-loader css-loader --save-dev
		
		css-loader处理.css文件，style是将我们的css文件的内容插入到我们html页面的head中的
		
	2、配置，两种方式	
		方式1：导入的时候
			require("!style-loader!css-loader!./style.css") // 载入 style.css
			
			弊端，以后导入所有的css文件，前面都得加一大堆loader的配置
	
		方式2：在终端打包的时候，在后面接上对.css的处理
			webpack entry.js bundle.js --module-bind "css=style-loader!css-loader"
			
			好处:不需要在每一次导入css的时候，都加上那个配置
```

### 配置文件

```
1、在项目根目录下，创建一个webpack.config.js，webpack默认的配置文件就叫这个
```

```
2、把我们原先在终端里面输入的入口文件，输出文件，loader都可以配置在我们webpack.config.js这个配置文件中
```

```
3、打包，在项目根目录下面运行 webpack即可，webpack会自动在当前我们的目录下找到webpack.config.js文件，然后解析里面的内容进行打包
```

### 使用插件

```
1、在项目中(本地)安装一个webpack的包
	npm i webpack --save-dev
	
2、插件的配置
	var webpack = require('webpack')
	
	plugins: [
	    new webpack.BannerPlugin('This file is created by zhaoda')
	]
	
	注意:
		plugins一定是和entry output module同级
```

### webpack打包的一些指令

```
webpack [参数] 入口文件 输出文件
```

```
期望:
	1、打包的时候，希望有进度  webpack --progress
	2、打包出来的东西能压缩一下 webpack --progress -p
	3、改了源文件，自动打包(自动刷新) webpack --watch
	4、如果我的配置文件不叫webpack.config.js了，我还想正常运行，肿么办? webpack --config 新的文件名称
	
注意:
	1、webpack后面的参数可以写多个
	2、压缩时候-p功能有限，使用uglify(webpack自带了)
	3、webpack后面的参数，写多少，写在哪里无所谓，但是要用空格分割
```

### 注意点说明

```
1、webpack其实是在我们项目上线之前才需要用到它打包压缩优化，这个是为了讲上面的知识点，所以用到它
```

```
2、使用webpack打包，只需要打包入口文件即可
```

```
3、默认情况下webpack只打包.js结尾的文件，如果要打包其它类型的文件，得安装配置loader
```

------

## Webpack+Vue构建项目

```
强烈建议：不要先使用脚手架，跟着我的节奏一步一步来
```

## 步骤(见下面)

### 创建一个必要的文件和文件夹

```
vue
	|-src (项目的源代码)
	|	|-main.js 项目打包的入口文件
	|	|-App.vue 项目启动看到的第一个组件(页面)
	|   |
	|-package.json (项目的配置文件)
	|-webpack.develop.config.js (开发阶段的webpack配置文件)
```

------

### 写文件中的代码

```
达到的目标:
	运行起我们的项目能看到Hell Vue
	
步骤:
	1、先写好源代码 
		App.vue
			template > Hello Vue
			
		main.js
			1、导包
			2、导入根组件
			3、创建项目的根实例，渲染App.vue
			
	2、打包
		前提:
			1、安装两个包 vue-loader vue-template-compiler css-loader
			npm i vue-loader vue-template-compiler css-loader --save-dev 
			
			2、在webpack.develop.config.js中配置loader
	
		打包:
			webpack --progress --config webpack.develop.config.js
			
	3、运行打包好的bundle.js文件
		1、新建一个index.html，导入bundle.js
```

#### 配置文件中(webpack.develop.config.js)的代码

```
见代码(我建议你们拷贝)
```

```
现在先写了打包的入口文件、输出文件
```

#### 写main.js中的代码

```
要写哪些代码?
	1、导入vue.js因为项目是基于Vue
	
	2、项目中导入根组件
	
	3、创建一个根实例 new Vue({
		el:'#app',
		渲染我们用户看到的第一个组件
	})

1、使用npm安装 vue
	npm i vue --save
```

#### 写App.vue代码

```
单文件组件
	https://cn.vuejs.org/v2/guide/single-file-components.html
	
在App.vue中写上 template里面有个根元素，里面写上一句话Hello Vue
```

------

## 最终的目标

```
更改源代码，自动打包，在浏览器中不刷新刷新按钮也能看到最新的效果
```

### webpack&webpack-dev-server的关系

```
webpack-dev-server 是 webpack的升级版，webpack里面有的东西它都有，webpack没有，他也有，比如(热更新)
```

```
共同点:
	都能打包，指令一模一样
	
区别:
	webpack-dev-server比webpack更强大
	
	webpack:生产阶段，使用webpack打包生成实实在在的物理文件(压缩，优化的)
	
	webpack-dev-server:开发阶段，不会生成实实在在的文件，文件生成之后放在浏览器的内存中，一般开发阶段不压缩(是为了方便调试)
	
补充:
	webpack-dev-server 底层基于node
```

### webpack-dev-server + `html-webpack-plugin`

```
webpack-dev-server 
	 作用:
	 	1、监控源代码更改，更改之后自动打包(bundle.js)，但是这个bundle.js不会生成一个真实的文件，生成在浏览器的内存中，效率高	
	 	
	 	2、自动打开浏览器，实现热更新(热重载，热加载)
	 	
html-webpack-plugin
	作用，以一个模版/参照文件，在内存中，生成一个index.html，它内部还会自动帮我们导入bundle.js
	
注意点:
	最终打包是使用webpack-dev-server 
```

### 写代码

```
目标:
	使用这两个第三方包，在`内存中`生成index.html和bundle.js，并且把项目运行起来，当更改源文件实现热更新
	
步骤:
	1、在内存中生成index.html，使用`html-webpack-plugin`第三方包
		参考:https://github.com/jantimon/html-webpack-plugin
		
		1.1 在项目根目录下建立一个参照文件 template.html，里面只需要写
			id=app的div即可，不要再写导入bundle.js的文件
			
		1.2 在我们的webpack.develop.config.js的plugins中配置我们html-webpack-plugin
			安装 webpack webpack-dev-server html-webpack-plugin
			npm i webpack webpack-dev-server html-webpack-plugin --save-dev
			
			配置:
				见代码
				
	2、使用webpack-dev-server 在内存中打包生成bundle.js，配置一些参数，会自动打开浏览器，实现热更新
		前提:
			安装 webpack-dev-server 这个全局包 
				npm i webpack-dev-server -g
				
		打包指令
			参考:https://webpack.github.io/docs/webpack-dev-server.html
			
			--port 6008 指定我们开启web服务时候的端口号
			--open 打包完毕，自动打开浏览器
			--hot 热更新
			
			webpack-dev-server --config webpack.develop.config.js --progress --port 6008 --open --hot
```

## 如何在我们项目中，简化webpack-dev-server打包的一长串指令

```
可以将这一长串指令，放在项目的package.json的scripts属性中，
给它创建一个键值对，键的名称就写dev，值就是`webpack-dev-server --config webpack.develop.config.js --progress --port 6008 --open --hot`

运行：npm run dev
```

------

## 项目中安装的包

```
1、vue
	在写main.js的时候，安装的，因为搭建的是vue项目
	安装方式：npm i vue --save
	
2、vue-loader vue-template-compiler css-loader
	打包App.vue的时候，需要安装
	安装方式:npm i vue-loader vue-template-compiler css-loader --save-dev
	
3、webpack webpack-dev-server html-webpack-plugin
	在内存中根据参照文件生成index.html
	安装方式: npm i webpack webpack-dev-server html-webpack-plugin --save-dev
```

------

## Webpack+Vue构建项目

### 步骤

```
1、创建项目中的必要的文件及文件夹
```

```
2、写main.js App.vue webpack.develop.config.js
```

```
3、打包
	vue-loader
```

### webpack-dev-server 和 html-webpack-plugin在开发阶段

```
html-webpack-plugin以参照文件在内存中生成index.html
```

```
webpack-dev-server 在内存中生成bundle.js
```

## vue-cli

```
前提：全局安装 
	npm/cnpm i vue-cli -g
参考:
	https://github.com/vuejs/vue-cli
步骤:
	1、先生成项目
		vue init webpack-simple vue_project
	2、在安装依赖的第三方包
	3、运行
注意点:
	cross-env 全局包，用来在终端中使用，将来设置我们的项目的环境的
```

## App.vue

```
头部
中间
底部

头部&底部，使用mint-ui的组件
```

### mint-ui的使用

```
移动端:https://mint-ui.github.io/#!/zh-cn
PC端：http://element.eleme.io/#/zh-CN

饿了吗出的一款基于 Vue 的移动端的WebApp使用的组件库

使用步骤：
	1、安装 npm install mint-ui -S
	
	2、集成到我们项目中
		import Mint from 'mint-ui'
		Vue.use(Mint)
		
	3、在需要的地方使用
		App.vue的头部、底部(Tabbar)
		
注意点:
	集成mint-ui的时候，导入样式，这个时候，需要配置对css样式的支持
	1、安装style-loader css-loader
	2、在webpack.develop.config.js中配置
	
	webpack2.x 
		 { 
            test: /\.css$/, 
            use: [
                { 
                    loader: 'style-loader' 
                },
                {
                    loader: 'css-loader'
                }
            ] 
          }
```

------

## 项目中集成路由，让中间的内容动态切换

### 步骤:

```
1、安装包
	cnpm i vue-router -S
	
2、集成到项目中来(main.js)
	import VueRouter from 'vue-router'
	Vue.use(VueRouter)
	
3、写代码
	html中写
		1、占位:
			router-view
		2、触发:
			router-link
	
	js中写
		1、创建/导入组件
		
		2、创建路由对象，设置路由规则
		
		3、注入到根实例中
```

------

## home.vue

### 轮播图

```
思路：
	1、获取数据
		使用vue-resource
	
	2、渲染轮播图
```

### 项目中使用vue-resource

```
1、安装 vue-resource
2、集成到项目中
	import VueResource from 'vue-resource'
	Vue.use(VueResource)
3、使用home.vue
	见代码
```

### 九宫格布局

```
mui
移动端的bootstrap

网址:http://dev.dcloud.net.cn/mui/

集成步骤:
	1、从github获取mui的包，把css，fonts拷贝到项目的静态资源文件夹
	
	2、我们在main.js导入mui.css，但是mui内部又要导入mui.ttf
	
	3、安装url-loader file-loader及配置加载mui.ttf文件
	
使用:
	九宫格布局
		http://www.dcloud.io/hellomui/examples/grid-default.html
		
	拷贝然后更改
```

------

## 新闻列表

```
实现步骤:
	1、跳转到新闻列表组件
		1.1 监听点击，触发路由
		1.2 新建新闻列表组件
		1.3 配置路由规则
	
	2、发送网络请求
	
	3、渲染
	
在新闻列表组件中显示时间的时候需要对服务器返回的时间进行过滤
	全局的过滤器
	
对时间进行过滤/格式化使用 momentjs
	网址:http://momentjs.cn/
	
momentjs的使用步骤
	1、安装
		npm install moment --save 
		
	2、使用
		 moment(时间).format(格式)
```

------

## 项目中用到的第三方包

### mint

```
应用场景:在项目的App.vue的头部和底部TabBar用到
安装:npm install mint-ui -S
```

### style-loader css-loader

```
应用场景:在导入mint-ui的样式的时候，使用的
安装 npm i style-loader css-loader --save-dev
```

### vue-router

```
应用场景:在App.vue中间内容需要动态替换的时候
安装: cnpm i vue-router -S // -S相当于--save
```

### vue-resource

```
应用场景:在home.vue中获取轮播图数据的时候
安装: cnpm i vue-resource -S
```

### url-loader file-loader

```
应用场景:在使用mui的时候，要加载字体文件.ttf
安装:cnpm i url-loader file-loader --save-dev
```

### moment

```
应用场景:在新闻列表格式化时间的时候
安装:cnpm i moment --S
```

## 新闻详情

```
思路:
	1、创建组件
	2、设置路由规则(传递id)
		
		在新闻列表中触发
		main.js中配置
		
	3、拿数据
	4、渲染
```

------

## 顶部返回&底部隐藏

```
达到的效果:
	1、非home组件 隐藏Tabbar，显示返回按钮
	2、home组件 隐藏返回，显示Tabbar
	
瓶颈:
	如何在App.vue中监控路由的变化
	watch
	
	watch属性的作用，能监控我们Vue实例中所有的属性值的更改
	
	写法:
		监控的属性名称:处理函数
		
	在我们这个地方要监控的是$route
```

### 声明式导航，编程式导航

```
声明式 router-link 事先写好在template
```

```
编程式 this.$router.xxx
```

### 步骤总结

```
1、在App.vue中监控到路由的更改
	watch ---> $route
	
2、通过v-show 决定显示还是隐藏返回按钮

3、通过动态绑定class 决定显示还是隐藏Tabbar

4、刷新页面在App.vue的created处理
```

------

## 评论(父子组件之间传值)

### 新闻详情、图片详情、商品详情

```
方式1:每一个地方都写相同的(不可取)
```

```
方式2:把评论的功能抽取出来，在需要的地方(新闻详情、图片详情、商品详情)集成进去(可取)
```

### 如何抽取评论组件

```
思路:
	1、把评论单独放在一个组件中，这个我们称之为子组件
	
	2、把需要集成评论子组件的组件(新闻详情、图片详情、商品详情)称之为父组件
	
需要做的事情:
	在父组件中把id号传给子组件即可
```

### 代码步骤

```
参考:https://cn.vuejs.org/v2/guide/components.html
```

```
1、新建评论子组件
```

```
2、父组件中集成子组件(代码写在父组件)
	2.1、导入
	2.2、注册
	2.3、使用

3、父组件传递id给子组件(父子组件中都需要写代码)
	
	父组件负责传递
		<subcomment :commentId="$route.params.newsId"></subcomment>
	子组件负责接收
		props:['commentId']	
	
4、子组件获取到id之后，实现自己的业务逻辑	
	4.1 画UI
	4.2 获取我们的评论列表，并且实现加载更多功能
		分页加载---> 思路
		
		代码:
			1、整个值来记录当前是多少页，每当点击加载更多的时候加一
			2、第一次要加载第一页的值
			
		加载更多:
			1、加载更多的事件
			2、把pageIndex+1，再调用发送请求的代码
			3、处理服务器返回的数据的时候，如果是非第一页，我们需要把服务器返回的数据，拼接cancat到原先返回的数据后面
		
	4.3 提交评论的功能
		1、监听按钮的点击事件
		2、获取文本域中的内容
			原始 虽说不推荐直接操作dom，但是如果真的要用，就用呗
```

​				

```
		3、提交给服务器(判断一下是否为空)
		4、提交成功之后的处理
			重新加载第一页
			文本域中的内容清空
			Toast提示一下
```

### 项目中集成类似与jquery的js类库

------

## 图片分享

### 图片列表

```
思路:
	1、触发home里面图片分享的点击
	2、创建一个图片列表组件
	3、加载图片分类和图片列表		
```

### 图片详情

思路:

	1、点击图片列表
	2、创建组件
	3、设置路由规则，把图片id传递过来
	4、拿着图片id，处理自己的业务逻辑

集成评论:
	1、在图片详情中导入评论子组件
	2、在图片详情中注册
	3、使用及传值

缩略图
	1、获取数据
	2、渲染(九宫格布局)
	3、使用vue-preview预览我们缩略图
		参考:https://github.com/LS1231/vue-preview
## 图片详情中的缩略图展现

```
步骤:
	1、发送网络请求，获取数据
		
	2、渲染UI
		九宫格布局
	
	3、使用vue-preview完成预览功能
```

### 图片预览

```
基于vue-preview
```

```
Github地址:https://github.com/LS1231/vue-preview
```

```
PhotoSwipe 例子	https://codepen.io/dimsemenov/pen/gbadPv/
```

```
使用步骤：
	1、安装
		npm i vue-preview -S
		
	2、集成到项目中
		导入
		xxx.use()
		
	3、在需要使用的地方再使用它
```

------

## 商品列表

### 步骤

```
1、先跳到商品列表
	创建goodslist.vue
	在home.vue中给商品购买添加router-link
	main.js中配置路由规则

2、获取数据

3、渲染
```

### 轮播的抽取

```
home.vue中的轮播图和商品详情中的轮播图是否可以抽取呢?
	是，因为它们的UI结构差不多，只是数据不太一样
	
如何抽取?
	经过仔细的分析，发现它们的写的UI的代码一样，只是url不一样
	
抽取步骤:
	1、新建一个轮播组件(subswipe.vue)
	
	2、集成到goodsinfo.vue
		导入
		注册
		使用
	
	3、goodsinfo.vue传递参数给subswipe.vue
		传递url
		接收方:subswipe中写props
		传递方:<subswipe xxx=ooo></subswipe>
		
	4、subswipe拿到url完成自己的逻辑
```

------

## 商品详情

### 步骤

```
1、跳转到商品详情
	创建组件newsinfo
	商品列表中触发(router-link)
	在main.js中设置路由规则

2、获取商品详情的数据

3、渲染
```

------

## 图文介绍

### 步骤

```
点击触发事件
```

```
跳转到图文介绍组件?(编程式导航)
	编程式导航 this.$router.push(xxx)
	创建组件，设置路由规则

根据id获取对应的数据

渲染组件
```

------

## 商品评论

### 步骤

```
点击触发事件
```

```
跳转到图文介绍组件?(编程式导航)
	编程式导航 this.$router.push(xxx)
	创建组件，设置路由规则
	
集成评论子组件把商品的id好传递给他即可
```

------

## 数量选择子组件传值给商品详情父组件

### 步骤

```
1、创建一个数量选择子组件(subnumber.vue)
	写好自己的业务逻辑
	
2、把subnumber.vue集成到父组件(goodsinfo.vue)
	导入
	注册
	使用

3、当子组件subnumber.vue中的值发生更改之后，把值传递给父组件(goodsinfo.vue)
	参考:https://cn.vuejs.org/v2/guide/components.html#自定义事件
	
	传递方:子组件，触发事件 $emit
	
	接收方:父组件，监听事件 $on
```

------

## 项目中用到的包

### vue-preview

使用场景:

	在图片详情预览的使用
	安装:npm i vue-preview -S
## 组件(Vue实例的生命周期)的生命周期钩子

```
参考:https://cn.vuejs.org/v2/guide/instance.html
```

### 概念

```
人的生命周期
出生 ---> 小学 --> 中学 --> 大学 --> 娶妻生娃 --> 慢慢变老 --> goodbye 

组件(Vue实例)生命周期
created ---> xxx  ---> destory
```

### 作用

```
给予用户机会在一些特定的场景下添加他们自己的代码
```

### 应用场景

```
created: 发送网络请求
beforeMount/mount:过渡动画
beforeUpdate/updated:过渡动画
beforeDestroy:
	记住该页面滚动的位置
	统计用户喜欢哪个组件,App埋点
```

------

## 非父子组件之间是如何传递值

```
就是使用公共的bus(bus就是一个公共的Vue对象)
```

```
参考:
	https://cn.vuejs.org/v2/guide/components.html#非父子组件通信
```

### 思路

```
还是使用我们自定义事件这种方式来传递
```

```
传递方：使用公共的Vue对象，触发事件
	bus.$emit('自定义事件名称',值)
	
接收方：使用公共的bus监听事件，实现处理函数
	bus.$on('自定义事件名称',处理函数)

注意点:
	1、传递值&接收值必须要有一个公共的Vue对象
```

### 当我点击了加入购物车，这个时候，把数量从商品明细组件传到App.vue这个组件

```
1、这两个组件是没有任何父子关系
```

### 步骤:

```
1、加入购物车事件处理
	提示加入购物车成功
	拿到子组件中的值

2、把数量选择子组件中的值传到App.vue

3、App.vue接收到goodsinfo.vue传递过来的值

4、App.vue拿到值之后，处理自己的业务逻辑
```

------

## Vuex

```
状态 === 数据
```

### Vuex是什么?

```
Vuex 是一个专为 Vue.js 应用程序开发的状态管理模
式。它采用集中式存储管理应用的所有组件的状态，并以
相应的规则保证状态以一种可预测的方式发生变化。Vuex
也集成到 Vue 的官方调试工具 devtools extension，
提供了诸如零配置的 time-travel 调试、状态快照导入
导出等高级调试功能。

管理我们所有组件中全局的一些数据
	Vuex

组件的局部的数据呢?
	.vue 中的 data
```

### Vuex它能做什么?

```
1、在多个组件之间实现数据的共享或是数据的存取
2、追踪我们数据的变化
```

### 应用场景(Vuex和公共的bus如何抉择?)

```
1、简单的情况下用bus
2、复杂的情况下用Vuex

3、中大型的单页面应用，并且需要更好地在组件外部管理状态
4、如果你的应用足够简单，杀鸡焉用牛刀
```

### 五大核心概念

```
state:相当于仓库，所有的存和取都要放在这里
	state定义的一般都是对象或是数组
	
getters:
	通过函数的形式，供外面获取的
	
mutations:
	同步，通过函数，让外面调用，存到state中的
	
actions:
	它不能直接往仓库中存，它要调用mutations，才能存到仓库中去

modules:多个仓库
```

### 如何写代码

```
前提：
	安装vuex,并且集成到项目
	参考:https://vuex.vuejs.org/zh-cn/installation.html
	
	import Vuex from 'vuex'
	Vue.use(Vuex)
写代码了:	
	1、建立Vuex对象
	2、注入到根实例中
```

------

## Vuex在项目中的使用的地方

```
存:在商品详情中，点击了加入购物车，存到了仓库中去了
	1、在创建好的store对象里面写如下代码
		state:{
			goodsList:[]
		},
		mutations:{
			函数(state,值){
				state.goodsList.push(值)
			}
		}
		
	2、点击加入购物车的时候，调用该函数
```

```
取/查:	
	App.vue中的购物车的徽标
		在store对象中，写如下代码
			getters:{
				函数名称(state){
					xxx
					return ...
				}
			}
	
	在购物车组件中取
删:
	购物车组件中删
```

### 项目中，购物车的数据在Vuex中应该怎么存

```
Vuex他是内存存储
```

```
Vuex中的state仓库里面存储的购物车的数据什么格式最合适?
	goodsList:[]
	
当点击加入购物车之后，我们必存的信息
	商品id、选择的数量
	
最终存储到Vuex仓库里面的数据，就是如下的样子
	[{goodsId:88,count:3},{goodsId:87,count:2},{goodsId:88,count:2}]
```

### 一些电商网站，加入购物车，是把购物车的数据存在哪里的?

```
京东:	
	未登录 存放在cookies
	登录 存放在京东的服务器
	
淘宝:
	必须要登录 
		存在到淘宝服务器
		
存放本地(cookie & localStorage)
	优势:减少服务器压力，减少数据库中不要的存储
	缺点:换了浏览器，换了电脑
	
存储在服务器端
	优势:换了浏览器，换了电脑，你加入到购物车中的东西还在
	缺点:占用服务器资源
```

------

## 今日项目中使用到的第三方的包

````
vuex:存储购物车数据的时候使用到了
安装:cnpm install vuex --save
````

## Actions

### 作用

```
异步的操作state中的数据
```

### 注意点

```
它不能直接拿到state中的数据进行操作
```

### 代码

```
actions中写一个方法
```

​	

------

## 购物车组件

### 购物车中存储的数据

```
[
	{goodsId:"87",count:2},
	{goodsId:"88",count:3},
	{goodsId:"87",count:3}
]

===>

发送请求:
	api/goods/getshopcarlist/87,88
```

### 购物车展示

#### 发送网络请求

```
工作任务如何做:
	拆解，各个击破
	
步骤:
	1、从vuex中获取到数组

	2、将原始数组，合并id和数量
		[
			{goodsId:"87",count:2},
			{goodsId:"88",count:3},
			{goodsId:"87",count:3}
		]
		
		===>
		var tempObj = {"87":5,"88":3}
	
	3、遍历上一步的key值，将其加入一个数组
		[87,88]

	4、调用上一步数组的join
		87,88
	
	5、拼接url、发送请求		
		
	6、把服务器返回的数据，动态加上count属性
		tempObj["87"]
		
	7、渲染之前最终的样子:
		[
			{
				id:87
				title:"华为",
				sell_price:2195,
				thumb_path:"xxx.jpg",
				count:5
			},
			{
				id:88
				title:"苹果",
				sell_price:6888,
				thumb_path:"apple.jpg",
				count:3
			}
		]
```

#### 开关出现了问题

```
当我点击某一个的时候，开关呈现同样的状态
```

```
解决办法:
	分开绑定即可
```

------

### 购物车里面的操作(统计信息)

```
步骤：
	1、UI搭建出来
	
	2、刚开始进来，重新计算
	
	3、监听Switch的切换，重新计算
	
	4、删除的时候，也需要重新计算
```

### 统计信息重新计算抽取出来

```
统计的是：只有开关打开的那一项
```

### 点击了开关的状态，需要做两件事

```
第一件:
	重新计算我们当前的总数量和总价格
	
第二件:
	更改删除按钮的样式
```

### 删除商品项的逻辑

```
步骤:
	1、给删除按钮添加点击事件，弹出框框，决定删除
	
	2、删除对应id的Vuex中的数据
		Vuex的mutations提供一个根据id删除商品的函数
	
	3、干掉购物车里面的数据即可
	
	4、重新统计
```

------

## 项目总结

### 搭建项目

```
步骤多，安装包的包也多
	webpack
	webpack-dev-server

	vue:
	.vue ---> vue-loader&css-loader&style-loader&vue-template-compiler
	
	提高开发效率
		html-webpack-plugin 开发阶段:在内存中生成index.html
		webpack-dev-server 开发阶段:在内存中生成bundle.js --hot --port
	
	App.vue
		main.js 导入App.vue
		创建一个根实例
```

```
vue提供了脚手架 vue-cli
	使用:https://github.com/vuejs/vue-cli
	建议：生成项目的时候  vue init webpack-simple my-project
```

### App.vue

````
上 : mint-ui header
中 : vue-router
下 : mint-ui tabBar
vue-preview
````

# 支付

## 支付宝、微信支付、银联支付

## 美团WebApp

```
买了一个商品准备去付款
```

```
当我点击下订单，会把我刚刚的信息，提交到美团的服务器
```

## 买买买，去结算

```
步骤:
	1、将我们的商品信息，价格信息，用户信息提交给我们的后台，生成订单信息
		前端的工作
		
	2、服务器接收到了请求，生成订单信息，重定向到支付界面
		order_no product_name   price  order_status
		1001      iphone6		28900     0(未支付)
										  1(已支付)
		
	3、支付界面，用户选择某种支付方式，当点击了确认支付之后，发送请求给我们公司的服务器
		前端的工作
	
	4、我们的服务器接收到这个请求之后，会生成相应平台的支付信息
	
	5、把生成好的对应平台(支付宝)的支付信息(很长)，返回个浏览器
	
	6、浏览器拿到这些之后，通过window.location.href="xxx",跳转支付宝了
		前端工作
	
	7、用户和支付宝交互，用户支付成功，扣用户的前，达到我们公司的支付宝账户
	
	8、支付宝发消息给我们自家的服务，告诉我们服务器，订单号为1001，已经成功的支付
	
	9、我们自家的服务器，把订单号为1001的支付状态，改成1(已支付)
```

------

## 支付宝支付步骤

### 文档

```
https://docs.open.alipay.com/203
```

```
建议：在真正需要使用的时候，再去看新的文档
```

### 哪些人参与

```
老板/财务
```

```
后台
```

```
前台:
	前端
	iOS
	Android
	
	openURL("/xxx")
	com.alipay.xxx
```

### 步骤

```
前提:
	我们公司和支付宝签约，一般是公司
	公司的老板/财务会拿着工商营业执照，公章，纳税征税
	
	商户的id:2088xxxxxxx   16位
	支付宝的合作商户
	
	后台会在我们公司支付宝账号后台的管理系统里面设置一些信息
	公钥:如何生成公钥&私钥
```

```
	RSA:
		公钥&私钥 	鸳鸯
		
		私钥加密  > 公钥解密

正式接入:(前后台要一起)
	后台会生成最终支付宝支付需要的信息
		https://mclient.alipay.com/home/exterfaceAssign.htm?alipay_exterface_invoke_assign_client_ip=47.74.6.253&body=美团订单-120885176348451504576595&subject=美团订单-120885176348451504576595&sign_type=RSA&notify_url=http://10.110.162.16:8966/paygate/notify/alipay/paynotify/wap&out_trade_no=120885176348451504576595&return_url=https://meishi.meituan.com/i/order/result/3917023245&sign=aBL95E1KWgc+HxjVaPhbLa8Xv7Kv+MU8wj+FZ3RHbSLrqvLjp6oq6rnLe6kBu9pX/dFwWsWaLyGq0S90L/UbqHHhyTN5Pt0QtFY+MxYQe6H419Bn8aygPzJ16occOZXl4Iysb/eEP36tSmGLXuehLKRd0S+jl1zwtFAUiP1uEJo=&_input_charset=utf-8&it_b_pay=1440m&alipay_exterface_invoke_assign_target=mapi_direct_trade.htm&alipay_exterface_invoke_assign_model=cashier&total_fee=128&goods_type=0&service=alipay.wap.create.direct.pay.by.user&seller_id=2088311465207164&partner=2088311465207164&alipay_exterface_invoke_assign_sign=_b_eno1_h_tx_hwb+_k_se_r9b_zyp_ss6_wm_r_dia_gox_w_p_f_u3pq_i2_st_p_p_dta_ken3_a==&payment_type=1
		
	前端：
		拿着这一些，调用window.location.href="xxxx"
```

------

## 项目压缩打包上线

### 最终要达到的目的

```
把生成好的html,js,css，发布到阿里云、新浪云
```

### 项目里面的源代码优化打包压缩等一系列操作

```
gulp
webpack
```

### webpack进行代码的压缩打包

```
步骤：
	1、新建一个配置文件，生产阶段专用的
	
	2、把开发阶段里面的配置文件的代码，拷贝一份到生产阶段里面去
	
	3、打包操作
		webpack 入口文件 输出文件
		webpack 配置文件.js
		项目中打包:webpack --config webpack.publish.config.js
		
	注意点：
		html-webpack-plugin作用
		
		开发阶段:根据参照文件，在内存中生成index.html
		生产阶段:根据参照文件，在目标文件夹(dist)生成一个实实在在的index.html
		
		上面两个都会自动帮我们导入bundle.js
```

### 发现的问题

```
1、bundle.js体积过大 1.61M
	浪费带宽，浪费用户流量，加载速度慢，用户体验不好
	
2、html也没压缩 1.03KB
```

### 如何优化

```
1、压缩bundle.js、压缩html、干掉不必要的注释
```

​	

### 压缩bundle.js(1.61--->821kb)

```
1、使用 babel 把我们Vue项目中的es6转成es5
	参考:https://babeljs.io/docs/setup/#installation
	
	使用babel:
		1、安装包
			cnpm i babel-loader babel-core babel-preset-env --save-dev
			
		2、在loader中配置
			rules: [
			    { test: /\.js$/, exclude: /node_modules/, loader: "babel-loader" }
			]
			
		3、在项目根目录下，建立一个babel的配置文件写上预设就行了
			{
			  "presets": ["env"]
			}
```

```
2、压缩js使用UglifyJs
	目前主要支持es5的压缩
	参考:
		https://cn.vuejs.org/v2/guide/deployment.html
		
	在plugins中，配置如下
		new webpack.DefinePlugin({
            'process.env': {
              NODE_ENV: '"production"'
            }
        }),
        new webpack.optimize.UglifyJsPlugin({
            compress: {
                warnings: false
            }
        })
        
 3、上面这两步之后，还会报错（是因为项目中使用vue-preview）
 	ERROR in bundle.js from UglifyJs
		Unexpected token: name ($vm) [bundle.js:38442,4]
		
 	解决办法，在loader针对vue-preview再配置个loader
 		{
            test: /vue-preview.src.*?js$/,
            loader: 'babel-loader'
      	}
```

### 压缩html

```
参考:https://github.com/jantimon/html-webpack-plugin
	搜索minify

参考:https://github.com/kangax/html-minifier#options-quick-reference
在plugins:[
  minify:{
     minifyCSS:true,//压缩css
     minifyJS:true,//压缩js
     collapseWhitespace:true,//压缩html
     removeComments:true//去除注释
 }
]
```

### 补充插件，每次打包之前，删除旧的dist目录下面的所有东西

```
clean-webpack-plugin
```

```
使用:
	1、安装 clean-webpack-plugin
		cnpm i clean-webpack-plugin --save-dev
```

### 进一步对bundle内容进行处理?

```
bundle.js为何压缩之后还如此之大?
	我们项目自己写的或是用到的 .js .css .图片 .字体文件
					第三方包都打包进入了bundle.js中
					
目标:就是把有些东西从bundle.js剥离出来，放在其它的.js .css .font
	
不要死记硬背，不明白抄我的	
	
1、抽离图片，字体文件

2、抽离第三方包

3、抽离样式文件
```

------

## 剥离bundle.js文件之图片，字体文件

```
loader: 'url-loader?limit=4000&name=fonts/[name]-[hash:5].[ext]'
```

## 剥离bundle.js文件中的第三方包（写三处）

```
CommonsChunkPlugin 抽离第三方包
```

```
第一个地方:
	entry:{
		生成的js文件名称:['']
	}
	
第二个地方:
	output有多个输出文件
	
第三个地方:
	在plugin中要配置一下
```

## 剥离bundle.js中的外部的css文件,压缩抽离的CSS

```
使用一个插件
参考:https://github.com/webpack-contrib/extract-text-webpack-plugin

使用步骤:
	1、安装 cnpm i extract-text-webpack-plugin --save-dev
	
	2、在loader中更改
		 {
	        test: /\.css$/,
	        use: ExtractTextPlugin.extract({
	          fallback: "style-loader",
	          use: "css-loader"
	        })
	      }
	      
	 3、在plugins中，使用插件
	 	new ExtractTextPlugin("抽离出来的css文件存在在哪里去")
	 压缩抽离的css样式
	 1：npm install --save-dev optimize-css-assets-webpack-plugin
	 2：导入：var OptimizeCssAssetsPlugin = require('optimize-css-assets-webpack-plugin');
	 3：在Plugin配置：new OptimizeCssAssetsPlugin
```

------

## 面试题

### Vue双向数据绑定原理

```
模型 ---> 视图
	1、绑定（正则扫描html找出v-xxx）正则
	
	2、监控对象(data)属性的更改（Object.defineProperty）数据劫持
	
	3、订阅者-发布模式
			收音机  订阅者
			
			中心【数组】
				html页面元素和data中的属性有对应关系了
				
				当我们更改data中属性的时候，他会找到html中与之对应的元素的值，更改为最新的模型的值
				
			只要当data中的属性更改，就会通知对应关系，找到对应的dom元素，更新页面上面的值

视图 ---> 模型
	视图 ---> 模型 ---> 视图
```

------

### 微信小程序

```
Angular + Vue +React
```

```
公众平台:
	微信小程序&微信公众号

地址:https://mp.weixin.qq.com/

https://mp.weixin.qq.com/cgi-bin/wx
```

### 开发文档

```
https://mp.weixin.qq.com/debug/wxadoc/dev/framework/MINA.html
```


