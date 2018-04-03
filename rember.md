
1:HTTP协议

2:前端安全

3：常用的三驾马车

4：基础知识，跨域，es6新的语法

5：Node.js的开发 ，expresss,koa等常用的框架

6：数据库知识

7：能封装业务组件和公用组件

8：在技术选型上，能给出你选择的方案是

9：前端性能优化

10:前后端分离

1：前端架构 ，设计模式

2:前端工程化开发 ，测试，打包，发布；

3：自己实现前端架构代码以及开发工具；


-------------------------------------------

  *从浏览器接受到url到开启网络请求线程；

  	·多进程的浏览器
  	·多线程的浏览器内核
  	·解析url
  	·网络请求都是单线程

  *开启网络线程到发出一个完整的http请求；

  	·DNS查询得到IP
  	·tcp/ip请求
  	·五层因特网协议

  *从服务器接受到请求到对应的后台接受到请求

  	·负载均衡
  	·后台处理

  *后台和前台的Http交互

  	·http报文结构
  	·cookie以及优化
    ·gzip压缩
    ·长连接与短连接
    ·http 2.0
    ·hhtps

   *单独拎出来缓存问题 ，http的缓存

   	·强缓存与弱缓存
   	·缓存头部简述
   	·头部的区别

   *解析页面的流程

   	·流程简述
   	·html解析，构建DOM
   	·生成css规则
   	·构建渲染树
   	·渲染
   	·简单层与复合层
	·chrome中的调试
	·资源的外链的下载
	·loaded和domacontentloaded 

 	*css的可视化格式模型
 		·包含块；
 		·控制框
 		·BFC
 		·IFC
 		·其他

 	*js 引擎解析过程

 		·js的解析阶段
 		·js的预处理阶段
 		·js的执行阶段
 		·回收机制


 	9. 其它（可以拓展不同的知识模块，如跨域，web安全，hybrid模式等等内容）


------------------------

请求头

Accept :接受类型

Accept-Encoding:浏览器支持的压缩类型如（gzip）

Content-Type:客户端发出的实体类型

Cache-Control:指定请求和响应应遵循的缓存机制  //强缓存的

If-Modified-Since:对应服务端的Last-Modified,用来匹配文件是否变动； //协商缓存的；

Expires: 缓存控制，在这个时间内不会请求，直接使用缓存，http1.0, http是服务端时间

Max-age: 在本地缓存多少秒 htt1

Cookie:有cookie并且同域名会带上的

Connection :当浏览器与服务器的通信时长连接如何处理

Host:请求的服务器url

Origin:最初的请求是从哪发起的

Referer:该页面来源URL（适用于所有类型的请求，）

User-agent:用户客户端的一些必要信息，如ua头部；



响应头部分

--------------------------------------------------------------------

Access-Control-Allow-Headers: 服务器端允许的请求Headers

Access-Control-Allow-Methods: 服务器端允许的请求方法

Access-Control-Allow-Origin: 服务器端允许的请求Origin头部（譬如为)

Content-Type：服务端返回的实体内容的类型

Date:数据从服务器发送的时间

Cache-Control:告诉浏览器或客户，什么环境安全可以缓存文档

Expires：应该在什么时候认为文档已经过期,从而不再缓存它

Max-age：客户端的本地资源应该缓存多少秒，开启了Cache-Control后有效

ETag：请求变量的实体标签的当前值

Set-Cookie：设置和页面关联的cookie，服务器通过这个头部把cookie传给客户端

Keep-Alive：如果客户端有keep-alive，服务端也会有响应（如timeout=38）

Server：服务器的一些相关信息

---------------------------------------------------------------------

解析 html ，构建dom树;  bytes -> character -> tokens -> nodes -> dom
                           字节    (字符)       指令     节点

解析ccs,    生成css树；

合并dom树和css树规则，生成render树；

布局render树（layout/reflow）

绘制 render树




















-----------------------------css 布局


1：水平居中

	.parent{text-alien:center;}

	.son{display:block;margin:0 auto;}

	.parent{position:relative;}  .son{position:absolute;left:50; transform:translateX(-50%);}

	.parent{display:flex; justify-content:center;}

2:垂直居中

	.parent{line-height:XXX;} .son{display:inline-block; verical-align:middle;}

	.parent{display:table-cell; verical-align:middle;}

	.parent{position:relative;} .son{position:absolute;top:50%; transform:translateY(-50%;)}

	.parent{display:flex; align-items:center;}


3:水平垂直居中

  .parent{line-height:XXX;text-align:center;} .son{display:inline-block;}

  .parent{display:table-cell; vertical-align:middle;} .son{ margin:0 auto;} 

  .parent{position:relative;} .son{position:absolute; top:50%;left:50%; transform:translate(-50%,-50%);}

  .parent{position:relative;} .son{position:absolute; top:0;left:0; right:0;bottom:0; margin:auto;}

  .parent{display:flex;justify-content:center;align-items:center;}



左边固定宽；右边自适应；

	.left{width:200px;height:500px;float:left;} .right{margin:210px; }

	.left{width:200px;height:500px;float:left;} .right{}  //bfc模式是可以开的；

	.parent{display:table;}.left{width:200px; display:table-cell;} .right{display:table-cell;}

	.parent{width:100%;heigth:100%;position:relative;} .left{width:200px;height:100%;backfround:red;position:absolut;left:0;top:0;}.right{left:210px; top:0;height:100%;right:0;background:yellow;}

	.parent{display:flex;} .left{width:200px;} .right{flex:1;}


左右固定：中间自适应：

	.left{float:left;width:200px;height:500px;margin-left:-200px;} .right{float:left;margin:left:-200px;width:200px;}  .center{float:left;width:100%;} .center_inderBox{margin:0 200px 0 200px;} 

	.parent{width:100%;height:100%; background: red; position: relative;} .left{width:200px;height:100%;backfround:red;position: absolute;left: 0;top: 0;}.right{background:yellow;position: absolute;right: 0;top: 0;height: 100%;width: 200px;}.center{position: absolute;left: 210px;right: 210px;top: 0;height: 100%;background: blue;}

	table{}

	flex;


------------------------------html






-------------------------------ajax

	var xhr = new XMLHttpRequset()

	xhr.open('GET','url',true);

	xhr.send();

	xhr.onreadystatechange = function(){
		if(xhr.readyState ==4){
			if(xhr.status ==200){
				success(response)
			}
			
		}
	}

	function success(data){
		responseText
	}


	向请求添加 HTTP 头。setRequestHeader('Content-type',"application/x-www-form-urlencoded") 


  跨域 ：

	1jsonp 

	2cors




	var xhr = new XMLHttpRequest(); // IE8/9需用window.XDomainRequest兼容

	// 前端设置是否带cookie
	xhr.withCredentials = true;

	xhr.open('post', 'http://www.domain2.com:8080/login', true);
	xhr.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');
	xhr.send('user=admin');

	xhr.onreadystatechange = function() {
	    if (xhr.readyState == 4 && xhr.status == 200) {
	        alert(xhr.responseText);
	    }
	};


	并且nginx中设置  proxy_cookie_dimain

	
	webpack.config.js：中的proxy;


	3window.name  （存值较大的）

	4document domain  iframe (主域相同，子域不同的)

	5postmessage  页面之前和窗口的传递的



  


	------------------------------------------

	setTimeout({
		this//指的是window;
	},1)

	


  	es6:----------------------------------------

  	let 和const

		const obj ={
			a；1，
			b:2
		}

		const obj.a =5; //可以的

		1:块级作用域

		2：


  	变量的结构和赋值；

		1:数组的解构和赋值

		2:对象的解构和赋值

		3:函数参数的解构和赋值


	对象的扩展
		1:	var a= 5;

			var obj={a} 等价于 obj ={a:a}
			var obj ={
				a,
				show(){

				}
			}

		2:Object.keys()   //获取对象的键值生成新的数组

	 	 :Object.values() //获取对象的值

		3:Object.assign() //合并新的对象；

		4:Object.defineProperty(data,'b'{
				set(){

					},
				get(){

				}
			}) 

		5：Object.is(obj1,obj2);

	Symbol: 不能添加属性，类似‘字符串的水平’

	let s = Symbol();




	数组的扩展：

	...arr1,...arr2 //将一个数组转为逗号分隔的参数序列；

	Array.from() //用于类似数组中创建一个新的数组

	Array.of() //创建一个新的数组

	Array.copyWithin()// 移动位置的










	函数的扩展
		1: 参数设置默认值（）
		2：参数的解构和赋值（）
		3:箭头函数的this始终指向定义时所在的对象，而不是使用时的对象;



	class:定义对象吧；


	class Person{
		constructor(name,age){
			this.name =name;
			this.age = age;
		}
	}


	class Person2 extends Person{
		constructor(name,age,sex) {
			super(name,age);
			this.sex ="boy";
		}

		// methods
	}

	var p1 = new Person('tom',18);

    var p2 = new Person2('jieck','20','boy');

	

	模板字符串:

		`i ${a} you `



	module export和import 

	Set和Map---------

	Set:本身就是一个构造函数，用来生成set()数据结构  (更多是数组)

	const set = new Set([1,2,2,3,3,3,4]); //[1,2,3,4];

	set.add()

	set.delete()

	set.has()

	set.clear()  //清除所有成员的值；


	Map对象就是简单的键值对映射。其中的键和值可以使任意值
	
	const map =new Map();

	const obj = {p:'hello'}
	
	map.set(obj,'content'); //设置值
	map.get(obj);//content  //获取值

	map.has(o);

	map.delete(o);

	map.has(o);

-----------------------------


Proxy:用于修改某些默认的操作；



get():用于拦截某个属性的读取操作

set():用于拦截某个属性的赋值操作

	
------------------------------

Object.defineProperty(obj, prop, descriptor)  //操作符的

obj
	要在其上定义属性的对象。
prop
	要定义或修改的属性的名称。
descriptor
	将被定义或修改的属性描述符。


var o = {}; // 创建一个新对象

// 在对象中添加一个属性与数据描述符的示例
Object.defineProperty(o, "a", {
  value : 37,
  writable : true,
  enumerable : true,
  configurable : true
});

// 对象o拥有了属性a，值为37

// 在对象中添加一个属性与存取描述符的示例
var bValue;
Object.defineProperty(o, "b", {
  get : function(){
    return bValue;
  },
  set : function(newValue){
    bValue = newValue;
  },
  enumerable : true,
  configurable : true
});








------------------vue.js--------------------------


 vue init webpack vue-cli

 cd vue-cli 

 cnpm install 

 cnpm run dev



--------------------------------------------------
//https://juejin.im/post/5a9b8417518825558251ce15?utm_medium=fe&utm_source=weixinqun

1：compured和methods 的区别

	methods:是个方法 ，你要点击执行一个方法；

	computed:是计算属性，实时响应的，当data里的值变化时，会做出响应的处理

	watch；是用来观察实例上的数据的变动

2：vue响应原理:


	通过Observer 对data 做监听，用Object.defineProperty，将要观察的对象，转化成getter/setter，以便拦截对象赋值与取值操作，并且提供了订阅某些数据项变化的能力；

	把template 编译成一段 document fragment, 然后解析 其中的 Directive ,然后得到directive 所依赖的数据项和update方法

	通过watch 把上述两部分结合起来，即把 directive 中的数据依赖通过wathcher 订阅在对应的oberver ，

	当数据有变化时，就会触发oberver的dep 上的 notify方法通知对应的watcher 的update ,进而触发directive的update方法来更新ＤＯＭ视图；

	








3：请说下封装vue的过程；

    组件化，开发效率高，易于维护 ，可复用性高

    Vue.extend():创建一个组件

    Vue.component()注册组件

    以在props中接受定义。而子组件修改好数据后，想把数据传递给父组件。可以采用emit方法



4:vuex:

	state       状态保存的器

	mutations : 修改数据的 

	action :    异步处理的

	getter :    计算属性的


5:Vue computed 实现

	------------------
	初始化 data，使用Object.defineProperty把这些属性全部转化为getter/setter

	初始化 computed,遍历computed里的每个属性，每个computed属性都是一个watch实例。
	每个属性提供的函数作为属性的getter,使用object.defineProperty转化。

	object.defineProperty getter依赖收集。用于依赖发生变化时，触发属性重新计算。


	------------------


	data中的数据直接对属性的get,set做数据拦截 而computed则建立一个新的watche

	在组件渲染的时候 先touch computer的getter函数，将这个getter函数订阅起来的

	touch完后。Dep.target 此时又变为之前那个用于更新组件的。再通过watcher.depend()将这个组统一加上这个订阅。




6： Vue differ 算法的实现
	逐步遍历newVdom的节点，找到他在oldVdom中的位置

	if (oldVnode === vnode)，他们的引用一致，可以认为没有变化。
	if(oldVnode.text !== null && vnode.text !== null && oldVnode.text !== vnode.text)，文本节点的比较，需要修改，则会调用Node.textContent = vnode.text。
	if( oldCh && ch && oldCh !== ch ), 两个节点都有子节点，而且它们不一样，这样我们会调用 updateChildren 函数比较子节点，这是diff的核心，后边会讲到。
	if (ch)，只有新的节点有子节点，调用createEle(vnode)，vnode.el已经引用了老的dom节点，createEle函数会在老dom节点上添加子节点。
	if (oldCh)，新节点没有子节点，老节点有子节点，直接删除老节点。



	

7：虚拟dom是如何工作的；

	(1)用JS表示DOM结构

		Velement(tagname,props,child){}



	(2)比较2棵虚拟ＤＯＭ树的差异

	(3)对真实的dom 进行最小化的修改



	https://blog.csdn.net/yczz/article/details/51292169

	javascript很快，用javascript对象可以很容易地表示DOM节点。

	Velement(tagname,props,child){}

	

	根据虚拟DOM树构建出真实的DOM树


	VElement.prototype.render = function() {
    //创建标签
    var el = document.createElement(this.tagName);
    //设置标签的属性
    var props = this.props;
    for (var propName in props) {
        var propValue = props[propName]
        util.setAttr(el, propName, propValue);
    }


    比较两者的差值

    我们很少跨级别的修改DOM节点，通常是修改节点的属性、调整子节点的顺序、添加子节点等。因此，我们只需要对同级别节点进行比较，

    修改节点属性, 用PROPS表示

	修改节点文本内容, 用TEXT表示

	替换原有节点, 用REPLACE表示

	调整子节点，包括移动、删除等，用REORDER表示


	(3).对真实DOM进行最小化修改
	

	上文深度优先遍历过程产生了用于记录两棵树之间差异的数据结构patches, 通过使用patches我们可以方便对真实DOM做最小化的修改


























