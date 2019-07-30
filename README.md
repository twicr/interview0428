# interview
# 每日三问——0428
> [github项目](https://github.com/haizlin/fe-interview?utm_source=ZHShareTargetIDMore&utm_medium=social&utm_oi=750848792785354752) 问题解答
# HTML
### 常见的浏览器内核都用哪些？并介绍下你对内核的理解
内核分为渲染引擎和JS引擎，由于JS引擎越来越独立，现在内核主要指渲染引擎，主要浏览器内核有
* IE浏览器：Trident
* Chrome和Safari：Webkit
* FireFox：Gecko
* Opera：Presto
# CSS
### 说说你对css盒子模型的理解
* 盒模型包括margin、border、padding、content
* 一般情况下盒子的width = border-left + padding-left + content + padding-right + border-right
* 一般情况下盒子的height = border-top + padding-top + content + padding-bottom + border-bottom
* css3提供新属性box-sizing，设置border-box后width和height为位置的值，content随width和height改变而改变
# JS
### 写一个获取当前url查询字符串中的参数的方法
使用for循环遍历
```javascript
function urlArgument(){
    var search = decodeURI(window.location.search);
    search = search.substr(1,search.length);
    var arr = search.split("&");
    var obj = {};
    for(var i = 0; i < arr.length; i ++){
      arr[i] = arr[i].split("=");
      obj[arr[i][0]] = arr[i][1];
    }
    return obj;
}
```
使用过map遍历
```javascript
var search = decodeURI(window.location.search);
search = search.substr(1,search.length);
var obj = {};
search.split("&").map(item => {
    const arr = item.split("=");
    obj[arr[0]] = arr[1];
})
console.log(obj);
```
