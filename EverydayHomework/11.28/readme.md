# 2018 年 11 月 28 日面试题

## 问答题

1. 请解释一下 CSS3 的 flexbox（弹性盒布局模型）,以及适用场景？
2. 常见的 error 类型有哪些？
3. 如何判断一个变量的具体类型？(尽量把方法写全)
4. \$(this)和 this 关键字在 jQuery 中有何不同？
5. 写出下列程序输出的结果

```javascript
//1)
function add(m) {
  return function b(n) {
    return n + m++;
  };
}
var add1 = add(070);
var add2 = add(050);
console.log(add1(010));
console.log(add2(010));
//2)
var foo = 1;
function baidu() {
  console.log(foo);
  var foo = 2;
  console.log(foo);
}
baidu();
//3)
var baidu = {
  count: 2,
  getBaiduCount: function() {
    return this.count;
  }
};
console.log(baidu.getBaiduCount());
var func = baidu.getBaiduCount;
console.log(func());
//4)
function Foo() {
  var i = 0;
  return function() {
    console.log(i++);
  };
}
var f1 = Foo(),
  f2 = Foo();
f1();
f1();
f2();
//5)
var func = function(m, n) {
  arguments[0] = 3;
  arguments[1] = 2;
  return m + n;
};
console.log(func(1, 1));
//6)
var obj = {
  "2": "a",
  "3": "b",
  length: 2,
  push: Array.prototype.push
};
obj.push("c");
obj.push("d");
```

写出 obj 最终的结构？

## 编程题

6. 试着编写一个 arrayMerge() 函数，实现该函数被调用时，传递任意数量的数组，返回一个合并且去重的数组（可不局限于一种实现）。
7. 封装原生 AJAX？
8. 题目描述
   实现函数 partialUsingArguments，调用之后满足如下条件：
   1、返回一个函数 result
   2、调用 result 之后，返回的结果与调用函数 fn 的结果一致
   3、fn 的调用参数为 partialUsingArguments 的第一个参数之后的全部参数以及 result 的调用参数
9. 题目描述：
   已知 fn 为一个预定义函数，实现函数 curryIt，调用之后满足如下条件：
   1、返回一个函数 a，a 的 length 属性值为 1（即显式声明 a 接收一个参数）
   2、调用 a 之后，返回一个函数 b, b 的 length 属性值为 1
   3、调用 b 之后，返回一个函数 c, c 的 length 属性值为 1
   4、调用 c 之后，返回的结果与调用 fn 的返回值一致
   5、fn 的参数依次为函数 a, b, c 的调用参数
   输入：var fn = function (a, b, c) {return a + b + c}; curryIt(fn)(1)(2)(3);
   输出：6
10. 写一段程序实现 10000000000 ===> 10,000,000,000