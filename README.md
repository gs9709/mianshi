

/* ajax 部分 */

### 什么是ajax？ ajax的作用是什么？ ajax的优缺点
异步的javascript和xml  ajax用来和后台进行交互，最大特点实现局部刷新
优点：通过异步模式，提升了用户体验；
      优化了浏览器和服务器之间的传输，减少不必要的数据往返，减少了宽带占用；
缺点：ajax不支持浏览器back按钮
      不容易调试
       安全问题，ajax暴漏了和服务器交互的细节

### 原生js ajax 请求有几个步骤？ 分别是什么？
1.创建XMLHttpRequest对象
2.规定请求的类型 url 以及是否异步处理请求；
3.发送请求
4.接受服务器响应数据

### ajax几种请求方式？ 他们的优缺点；
post  get
区别： post比get安全（post参数在请求体中，lget在url上面）
get传输比post快，根据参数决定的
post传输文件理论上没有大小限制  get传输文件大小大概7-8k左右
get获取数据，post上传数据

###  什么情况下造成跨域：
浏览器有一个同源策略限制（域名，端口，协议） 如果不同源就会造成跨域  

### 跨域解决方式有哪些：
jsonp只能解决get跨域（问的最多）
原理：动态创建一个script标签。利用script标签的src属性不受同源策略限制 可以请求第三方服务器的内容
步骤：
创建一个script标签
script的src属性设置接口地址
接口参数必须要带一个自定义函数名。要不然后台无法返回数据。
通过自定义函数名去接受后台返回的数据；

CORS:跨域资源共享
  原理：服务器设置Access-Control-Allow-OriginHttp响应头，浏览器将会允许跨域请求。
  限制：浏览器需要支持html5 可以支持post put等方法
  
  缺点：需要后台配合，不怎么用
  Access-Control-Allow-Origin: *              //允许所有域名访问，或者
  Access-Control-Allow-Origin: http://a.com   //只允许所有域名访问

### http常见的状态码：
  2xx：表示成功处理了请求的状态吗
  3xx：表示要完成请求，需要进一步操作，通常这些状态码用来重定向
  4xx：这些状态吗表示请求可能出错，
  5xx: 表示服务器后台的错误
  
  具体自己遇到的：
    404：服务器找不到请求的网页（url拼错）
    403：服务器拒绝请求
    400：服务器不理解请求的语法
    

### ajax解决浏览器缓存问题：
1.在url后面加上一个随机数 Math.random()
2.在url加时间戳 new Date().getTime();
3.如果使用的jq，直接设置cache为false





/*css*/

### css盒子模型：
标准的盒子模型：宽度 = 内容的宽度（content） + border + padding + margin

### box-sizing ：
用来控制元素的盒子模型的解析模式 默认为content-box

### css选择器有哪些？那些属性可以继承？
id ，class 标签 后代选择器 伪类选择器 子选择器 通配选择器

可继承：font-size ， font-family color
不可继承： width margin padding height

### css3新增伪类：
P:first-of-type 
p:last-of-type
p:nth-child()

### 如何居中div ？ 如何居中一个浮动元素？ 如何让定位的div居中
div ：margin：0 auto
浮动居中：绝对定位+top(50%) + left(50%) + -(width/2) + -(height/2)
定位居中：border: 1px solid black;
position: absolute;
width: 200px;
height: 100px;
margin: 0 auto;
left: 0;
right: 0;
 

### display有哪些值：

block：
none：
flex：
inline-block：
table：

### position 的值：
static：默认 按照正常文档进行排列
relative：相对定位
absolute：决定定位
fixed：固定定位





### 为什么要初始化样式：
因为浏览器的兼容性问题，不同的浏览器对一些标签的默认值是不同的。如果没队css进行初始化会出现浏览器
之间的差异；

### px 和 em 的区别：
两者都是长度单位，去呗是px的值是固定的，指定多少就是多少，em的值会继承父级元素的字大小；


### 阐述以下css sprite：
将一个页面所设计的所有图片都包含到一张大图上去，然后利用css 的 background-image bg-repeat 
bg-position 的组合进行背景定位，利用css sprite能够很好的减少网页的http请求，大大提高网页的性能


### style标签写在body后和写在body前有什么区别？


### 设置元素浮动后，该元素的display自动变成block


### css媒体查询：九二一为不同的大小和尺寸的媒体定义不用的css 适应不用的设备显示；



/* es6*/

### 说出五个es6的新特性：
let const 关键字    用于声明旨在块级作用域起作用的变量  用于声明一个常量
解构赋值 一种新的变量赋值方式，
promise对象
class类定义类
set结构 map结构

### 箭头函数需要注意的地方：
当动态要求上下文的时候，就不能使用箭头函数了 也就是this的固话
1.在使用 => 定义函数的时候，this的指向是定义是所在的对象   而不是使用时候所在的对象
2.不能够使用arguments对象
3.不能够用作构造函数 就是说 不能使用new命令会报错

### 手写一个promise


### es6的模板语法
${xx} 这种形式，在es5的我们拼接字符串和变量的时候需要i使用 "aa" +b+"aa" 有了es6的模板
就很好写了；




/* js */

### 数组
常用的数组方法：
map : 将数组的每个元素调用一个提供的函数，结果作为一个新的数组返回，并没有改变原来的数组； 
push ： 在数组最后添加新的元素，此方法改变了数组的长度
unshift 
shift
pop ： 在数组后面删除最后一个元素，并返回数组 此方法改变了数组的长度
filter： 将所有数组元素进行判断，将满足条件的元素作为一个新的数组返回
forEach ： 将数组的每个元素执行提供的函数，没有返回值 住一个map进行区别
some ： 用于检测数组中的元素是否满足指定条件（函数提供）如果有一个元素满足条件 则表达式返回true，剩下的元素不在执行检测，
如果没有满足条件的元素，则返回false。不会改变原来的数组
reduce ：相当于一个函数累加器，接受一个回调函数的结果，然后将前一次的函数结果在和下一次的数据再次执行此回掉函数
isArray  
concat
join ： 此方法也是讲数组转化为字符串
splice 
toString：此方法将数组转化为字符串

### 字符串 
concat ：链接多个字符串
indexOf : 返回字符串中检索指定字符第一次出现的位置
charAt（index）: 返回指定索引位置的字符
substring：提取字符串中指定的索引号之间的字符
substr :从起始索引号提取字符串中指定数目的字符
slice:提取字符串的片段，并在新的字符串中返回被提取的部分
split： 将字符串分割成子字符串数组
length 
tpUpperCase: 将字符串转化成大写
trim： 去除字符串首位空白

数组去重（三种）：
遍历数组法：
function quchong(arr){
        let temp = [];
        for(let i= 0; i < arr.length;i++){
            if(temp.indexOf(arr[i]) == -1){
                temp.push(arr[i])

            }
        }
        return temp;
    }

数组下标判断法：
实现思路：如果当前数组的第i项在当前数组中第一次出现的位置不是i，那么表示第i项时重复的，忽略，否则存入

function unique(arr){
let hash = []
for(let i =0; i < arr.length;i++){

      if(arr.indexOf(arr[i]) == i){
            hash.push(arr[i])
      }

}

return hash;

}






es6去重：
function unique(arr){
      return Array.from(new Set(arr))
}































