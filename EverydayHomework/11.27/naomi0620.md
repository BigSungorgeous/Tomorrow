
## 1 说出3种web安全问题

- xss 攻击 服务器对于用户提交内容过于信任 用户将输入内容中有script脚本 
- csrf 跨域请求伪造 服务器对于浏览器过于信任 将网站链接放入假网页中的浮动窗口 伪装用户向服务器发送请求 
- msql语句注入 恶意将sql代码链接到表单提交信息后
## 2 this指向
    let fun=()=>{
     console.log(this.foo); 
        
    } 
    let c={ 
    foo:'foo', 
    baz:'bar', 
    say(){ 
    fun();
    (function(){ 
    console.log(this.baz); }()) } } 
    var foo='baz'; c.say();
    baz undefined

## 3.数组移除第一个元素的方法有哪些？ 
* shift
* 从下标为1的元素开始复制一个新数组 
* 先变成字符串 然后slice（1） [...str]

## 4.使元素消失的方法有哪些？##
>   display:none visibility:hideen opacity:0
## 5.var arr=[]; console.log(typeof arr) ??? Object typeof 会返回几种数据类型 ##
>   number boolean string null undefined object Symbol

## 6.使用js，返回1到400所有自然数中一共出现过多少次“1”，并返回出现次数##
    let sum=()=>{
    let num=0;
    for (let i=0;i<400;i++) {
    let f=i.toString(); 
    let d=f.indexOf("1") 
    if(d!=-1){ let arr=[...f];
    arr.forEach(v=>{ if(v=="1"){ num++; } }); } } 
    return num; } 
    console.log( sum() )

## 7.ajax请求的时候get 和post方式的区别 ##
 *   get 将传输的数据放在链接后 不安全且有大小限制 
  *  post方法把消息放在http请求头部 更安全

## 8.”==”和“===”和Object.is()的不同 ##
*   == 只比较值不比较类型
*   === 不仅比较值也比较类型 NaN===NaN false +0===-0 true 
*   Object.is() 值与类型都比较 NaN===NaN true +0===-0 false 

## 9.js有几种函数调用方式?##
* 1.作为一个函数调用 function foo(){} foo();
* 2.作为一个对象的方法 Obj.sayName() 
* 3.作为构造函数 
* 4.通过 call（） apply（）

## 10.js实现对象的深拷贝浅拷贝##
 *  浅拷贝 将一个数组对象内容 通过[...arr] 或 object.assign()复制对象 复制另一个数组内容
   深拷贝 通过JSON.stringify () JSON.parse() 用for in遍历循环 用arr.forEach()方法遍历复制