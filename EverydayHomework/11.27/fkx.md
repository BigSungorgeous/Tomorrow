1.3种web安全问题
	xss攻击：通过document.cookie盗取cookie。
	攻击方式：在浏览器发送HTTP请求时，xss代码出现在请求的url中，作为参数提交给服务器，服务器响应返回，相应结果中包含xss代码，最后浏览器解析执行。
	CSRF攻击：通过恶意代码发送HTTP请求，执行此恶意代码改变服务器端数据的值。改变用户的cookie，使得黑客可窃取信息。
	CSRF防御：严格设置cookie的域，尽量使用post传值，页面链接尽量少的暴露隐私信息
	安全控制：很多网址，会有更新，删除，插入的操作。若未限制用户的操作权限。容易误删其他用户的信息。

2.baz   undefined

3.   arr.shift()      var newarr=arr.slice(1)    var newarr=arr.splice(1)    
    
   var brr=[1,2,3,4,5,6]
   var arr=[]
   brr.forEach(function(elem,index,brr){
	if(index>0){arr.push(elem)}
   })
   console.log(arr)

4.dispaly:none;
   visibility:hidden;
   opacity:0;
   为元素添H5属性hidden；
   width:0;height:0;

5.object

6.  
      let a=0;
      for( let i = 0 ; i < 400 ; i++){
	let str="";
	str+=i;
	for( let j = 0 ; j < str.length ;j++){
		if(Object.is(str[j],"1")){
			a++;
		};
	};
       };
       console.log(a);

7.	GET请求会将参数跟在URL后进行传递
	POST请求是将参数作为HTTP消息的实体内容发送给服务器

8.==只比较内容不比较类型
  ===既比较内容又比较类型

9.function fkx(){};
   fkx();

   var fkx=function(){};
   fkx();

   原型的方法属于函数，可调用

   apply  ， call  ，  bind  改变this指向，也属于函数调用
  
   实例化对象的构造函数调用

10.深浅拷贝主要体现在数组与对象的拷贝

    浅拷贝是拷贝的地址，实现的是对地址的引用

    深拷贝是深度的克隆


   
