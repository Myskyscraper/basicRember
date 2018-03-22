


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

  	jsonp:只能实现get 格式的；




  	document.domain:主域名相同的；

  	
  	location.hash+ iframe跨域的


  	window.name


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

		2:Object.keys()   //获取对象的键值

		3:Object.assign() //合并新的对象；

		4:Object.defineProperty(data,'b'{
				set(){

					},
				get(){

				}
			}) 





	函数的扩展
		1: 参数设置默认值（）
		2：参数的解构和赋值（）
		3:箭头函数的this始终指向定义时所在的对象，而不是使用时的对象;



	class:定义对象吧；



	模板字符串:

		`i ${a} you `



	module export和import 


------------------vue.js--------------------------

 vue init webpack vue-cli

 cd vue-cli 

 cnpm install 

 cnpm run dev













