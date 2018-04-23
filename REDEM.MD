1. 盒模型
  盒模型是css布局的基石，它规定了页面内元素如何显示，以及元素之间相互关系，包括margin，padding，border和content

2. 
  行内元素：a,b,span,input,strong,b,select,button,textarea
  块级元素：div,ul,li,dl,dt,dd,p,h1-h6,blockquote
  空元素：link，meta，br，hr，input，img

3. css实现垂直水平居中

4. src与href
  href是指向网络资源所在位置，建立和当前元素或文档之间的连接，常用作超链接
  src是指向外部资源的位置，指向的内容将会嵌入到文档中当前标签所在位置

5. 什么是css hack？
  一般来说就是针对不同浏览器写的不同的css，就是css hack
  ie浏览器hack一般又分为三种，条件hack、属性级hack、选择符hack

6. 同步和异步的区别
  同步是阻塞模式，异步是非阻塞模式。
  同步就是指一个进程在执行某个请求的时候，若该请求需要一段时间才能返回信息，那么这个进程就会一直等下去，直到收到返回信息才继续执行下去。
  异步是指进程不需要一直等下去，二是继续执行下面的操作，不管其他进程的状态。当有消息返回时系统会通知进程进行处理，这样可以提高执行的效率。

7. px和em的区别
  px和em都是长度单位，但是px值是固定的，但是em的值不是固定的，并且会集成父级元素的字体大小。
  浏览器默认字体高度都是16px。所以未经调整的浏览器都符合1em=16px

8. 什么叫优雅降级和渐进增强
  渐进增强 progressive enhancement：
  针对低版本浏览器进行构建页面，保证最基本的功能，然后再针对高级浏览器进行效果、交互改进和追加功能达到更好的用户效果

  优雅降级 graceful defradation
  一开始就构建完整的功能，然后再针对低版本浏览器进行兼容。

  区别：
  1.优雅降级是从敷在的现状开始，并试图减少用户体验的供给
  2.渐进增强则是从一个非常基础的，能够起作用的版本开始，并不断扩充，以适应未来环境的需要。
  3.降级意味着往回看；而渐进增强则意味着朝前看，同时保证其根基出于安全地带

9. 浏览器的内核
  ie：trident三叉戟
  Firefox：gecko
  safari：webkit
  opera：曾经presto，现在blink
  chrome：blink



  javascript：
1. 实现函数克隆： 
  function clone(obj){
    var o;
    switch (typeof obj){
      case "undefined":
        break;
      case "string":
        o = obj + "";
        break;
      case "number":
        o = obj - 0;
        break;
      case "boolean":
        o = obj;
        break;
      case "object":
        if(obj === null){
          o = null;
        }else{
          if(Object.prototype.toString.call(obj).slice(8,-1) === "Array"){
          o = [];
          for(var i = 0; i < obj.length;i++){
            o.push(clone(obj[i]));
          }
        }else{
          o = {};
          for (var k in obj){
            o[k] = clone(obj[k]);
          }
        }
        }
        break;
      default:
        o = obj;
        break;
    }
    return o;
  }


2. 数组去重
  var arr1 = [1,2,2,3,3,3,4,5,6,6],
      arr2 = [];
  for(var i = 0,len = arr1.length; i< len; i++){
    if(arr2.indexOf(arr1[i] < 0){
      arr2.push(arr1[i]);
    })
  }
  document.write(arr2);