1.
    SQL注入：URL里面如果有对数据库进行操作的参数时，要做一下特殊的处理，
否则被别有用心的人利用的话就可能酿成大错，轻则用户信息泄露，重则数据库被删
    XSS 跨站脚本攻击：恶意攻击者往Web页面里插入恶意Script代码，当用户浏览该页之时，嵌入其中Web里面的Script代码会被执行，从而达到恶意攻击用户的目的。
    CSRF 跨站请求伪造：跨站点参考伪造通过在访问用户被认为已经通过身份验证的Web应用程序的页面中包含恶意代码或链接来工作。 如果该Web应用程序的会话没有超时，攻击者可能执行未授权的命令。

2.
    undefined
3.
    第一种：
    var arr=[1,3,5,7];
    function curtail(arr){
        var m = arr.shift();
        return arr;
    }
    console.log(curtail(arr))

    第二种：
    var arr=[1,3,5,7];
    function curtail(arr) {
        return arr.filter((ele,idx)=>idx !== 0 );
    }
    console.log(curtail(arr))

    第三种：
    var arr=[1,3,5,7];
    function curtail(arr) {
    var m = arr.splice(1);
        return m;
    }
    console.log(curtail(arr))

    第四种：
    var arr=[1,3,5,7];
    function curtail(arr) {
    var m = arr.slice(1);
        return m;
    }
   console.log(curtail(arr))

4.
    opacity:0;
    visibily:hidden;
    hidden:hidden;
    display:none;

    position:absolute;
    top:-100px;
    left:-1000px;

    widht:0;
    height:0;

    transform:scale(-10);
    transform:translate(-100px,-100px)

5.
    object

6.
     function cs(num, length) {
        var numstr = num.toString();//转化为字符串
        var m = numstr.length; //1-400的长度为400;
        if (numstr.length >= length) {
            return numstr;
        }
        for (var i = 0; i < length - m; i++) {
            numstr = "0" + numstr;
        }
        return numstr;
    } //调用函数cs，使用for循环一个个比较 
    var n;
    var result = 0;
    for (n = 1; n <= 400; n++) {
        var numstr = cs(n, 3);//n=1-400
        for (s = 0; s < numstr.length; s++) {
            if (numstr[s] == 1) {
                result += 1;
            }
        }
    }

7.
    （1）使用Get请求时,参数在URL中显示,而使用Post请求,则不会显示出来； 
    （2）Post传输的数据量大，可以达到2M，而Get方法由于受到URL长度的限制,只能传递大约1024字节. 
    （3）Get请求请求需注意缓存问题,Post请求不需担心这个问题； 
    （4）Post请求必须设置Content-Type值为application/x-form-www-urlencoded； 
    （5）发送请求时,因为Get请求的参数都在url里,所以send函数发送的参数为null,而Post请求在使用send方法时,却需赋予其参数； 
    （6）GET方式请求的数据会被浏览器缓存起来，因此其他人就可以从浏览器的历史记录中读取到这些数据，例如账号和密码等。在某种情况下，GET方式会带来严重的安全问题。而POST方式相对来说就可以避免这些问题。

8.
    ==：比较运算符，两边值类型不同的时候，先进行类型转换，再比较:
    +0等于-0
    NaN不等NaN

    ===：严格比较运算符，不做类型转换，类型不同就是不等:
    +0等于-0
    NaN不等NaN

    Object.is()是ES6新增的用来比较两个值是否严格相等的方法，与===的行为基本一致:
    +0不等于-0
    NaN等于自身

9.
    一、作为一个函数调用
    function myFn(a, b) {
    return a + b;
    }
    myFn(10, 2);

    二、函数作为方法调用
    var myObject = {
        firstName: "huang",
        lastName: "weisheng",
        fullName: function() {
            return this.firstName + this.lastName;
        }
    }
    myObject.fullName();

    三、使用构造函数调用
    function myFn(arg1, arg2){
        this.firstName = arg1;
        this.lastName = arg2;
    }
    var x = new myFn("huang", "weisheng");
    x.firstName;

    四、作为函数方法调用
    call() 第二个参数开始为call 的参数
    function myFn(a, b) {
        return a + b;
    }
    myObject = myFn.call(myObject, 10, 2);


    apply() 第二个参数为数组
    function myFn(a, b) {
        return a + b;
    }
    myArray = [10, 2];
    myObject = myFn.apply(myObject, myArray);

10.
    深拷贝:
    可以通过JSON对象的方法，来进行对象的深拷贝,相当于复制粘贴，可拷贝属性、方法
    function deepClone(arr){
        var obj=JSON.parse(JSON.stringify(arr));
        return obj;
    }
    var newarr=new deepClone(arr);

    浅拷贝:
    【利用for in ，遍历对象、数组...】
    只可拷贝对象的属性的引用，不能拷贝对象的方法
    var arr=["21","你好","hellow"];
    function simpleClone(initialObj){
        var obj={};
            for(var i in initialObj){
            obj[i]=initialObj[i];
            }
        return obj;
        }
    var newarr=new simpleClone(arr)