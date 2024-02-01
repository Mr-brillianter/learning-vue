# 1.    本地环境搭建和命令：

1.到官网下载node.js二进制文件并安装

2.运行下列代码：

```shell
npm install -g cnpm #可选，安装cnpm，防止npm连网太慢
cnpm create vue@latest #项目名不应包含大写，后续选项默认选择关，几乎等同于init
cd <项目名>
cnpm install #安装依赖
```

•    推荐的 IDE 配置是 **Visual Studio Code + Volar** 扩展。

•    要了解构建工具 Vite 更多背后的细节，请查看 Vite 文档。

**运行**，并设置端口127.0.0.1:5271，默认不暴露

```shell
#开发环境
cnpm run dev 
# 生产环境
cnpm run build
```

# 2.语法学习

当我们修改了Vue文件后，立即就会更新到对应的网页，堪称**神奇的自动更新编译！**

## 2.1空Vue文件

一个空网页的代码如下：

```javascript
<template>
<你的html代码>
</template>

<script >
export default{
  data(){
    return{
      <需要导出的以供上面html使用的变量，形式为“变量:值”的字典>
    }
  }
}
</script>

<style >
</style>
```


数据绑定，js导出变量绑定到前端，模板中需要用双括号来表示变量，即\<p>{{ msg }}\</p>，脚本中需要msg:'神奇的语法'类似的字典形式来输出变量
## 数据绑定
```javascript
<template>
<p>{{ msg }}</p>
</template>

<script >
export default{
  data(){
    return{
      msg:'神奇的语法'
    }
  }
}
</script>

<style >
</style>
```
## 组件导入
同时导出数据和组件:
```javascript
<script >

//1、导入组件
import comp_test from "./components/comp_test.vue";

export default{
  data(){
    return{
      msg:'神奇的语法'+'sad',
      
    }
  },
  //2、script导出组件
  components:{comp_test}
}
</script>

<template>
<p>{{ msg}}</p>
<p>{{\n}}</p>
// 前端使用组件
<comp_test/>
</template>

<style >
</style>
```
**常见问题**：导入组件时需要做三步，并且import时不能有中括号，即
```vue
//正确
import von from "./components/von.vue";
//不显示
import {von} from "./components/von.vue";

```


## style的使用
```javascript
// 在div中声明，某个标签使用了风格的class，这里是myclassfont1
<template>
<div class="myclassfont1">{{ msg2}}</div>
</template>

<style >
// .class名{内部设置class的style}
.myclassfont1{
  font-size: 12px;
  color:blueviolet
}
</style>
```
## v-if和else、elif：条件语句

v-if是v-if="<语句>"，和v-else搭配组成了if-else语句；和
v-else-if搭配组成if-elif语句，比如
```html
<div v-if="type=='A'">类型是A</div>
<div v-else-if="type=='B'">类型是B</div>
<div v-else-if="type=='C'">类型是C</div>
<div v-else>类型不是ABC</div>
```
以上代码利用type判断实现标签的选择性内容显示
### v-show
v-show和V-if基本一致，但开销不一样

## v-for 循环语句
```vue
<template>
  <button v-on:click="count++">{{ count }}这里</button>
  <div>{{ count }}这里</div>
</template>

<script>
export default{
    data(){
        return{
            count:0
        }
    }
}
</script>
```
## script setup：免除export，自动暴露

## v-on 事件触发
语法：

v-on:<事件>=“<函数或表达式>”

其中v-on等价于@
```vue
<template>
<button v-on:click="count++">{{ count }}这里</button>
<div>{{ count }}这里</div>
</template>

<script>
export default{
    data(){
        return{
            count:0
        }
    }
}
</script>
```

当为函数（或方法）时，使用前需要导出，即
```vue
<template>
<button v-on:click="AddCount">{{ count }}这里</button>
</template>

<script>
export default{
    data(){
        return{
            count:0
        }
    },
    methods:{
        AddCount(){
        this.count++
    }
    }
}
</script>
```
需要注意的是，使用变量要用this.来指定
## 事件读取和将网页事件拿到后端
将上述函数增加参数，就会自动获取到对应的事件，并且这个事件是
原生元素的“引用”，也就是可以直接去修改
```vue
<template>
<button v-on:click="AddCount">{{ count }}这里</button>
<button v-on:click="AddCount2">你好</button>
</template>

<script>
export default{
    data(){
        return{
            count:0,
            count2:0
        }
    },
    methods:{
        AddCount(e){
            this.count++
            console.log(e)
    },
        AddCount2(e){
            this.count2++
            console.log(e.target.innerHTML)
            e.target.innerHTML=this.count2
    }
    }
}
</script>
```
上述代码点击第二个框后，可以直接改变html标签的写法，非常恐怖~

## es6是什么？不是elastic而是js
ECMAScript 6，也被称为ES6，是JavaScript语言的一个重要版本。

ES6在2015年正式发布，它引入了许多新特性，以解决ES5中存在的限制和不足。以下是ES6的一些主要特性：

+ 类（Classes）：ES6中引入了类的概念，使得对象原型的写法更加清晰和面向对象。

+ 模块化（Modules）：ES6支持原生的模块化功能，允许开发者使用import和export关键字来导入和导出模块。

+ 箭头函数（Arrow Functions）：提供了更简洁的函数语法，并且this的值在箭头函数中是固定的。

+ 模板字符串（Template Strings）：允许嵌入表达式的字符串文字，使用反引号（`）包围。