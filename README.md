### project_vue

#### 前端框架作用
* 框架就是给了规则,并实现细节
  - 开发者按照规则,去实现业务逻辑
* 帮助我们去节省DOM操作的实现细节,完全的丢弃DOM的思维
  - 将数据与页面的元素挂钩
* 双向数据绑定
  - 页面改变影响内存
  - 内存改变影响页面
* Object.defineProperty就是Vue.js实现双向数据绑定的基本代码
  - Vue兼容IE9及以上,因为Object.defineProperty

#### vue启动
* 1:引包
* 2:创建对象(启动Vue) 
  - `new Vue(选项);`
* 3:页面中留坑 `<div id="app"></div>`
  - el:坑  
  - vue将template属性结合data属性，将数据渲染到el指定的坑中
  - {{可以使用data中的属性}} 插值表达式,也可以调用函数，也可以三元表达式
  - v-model="data中的属性"
  - `new Vue(options)`
  - el:字符串或者DOM元素 （目的地）
  - data:对象或者是函数（数据） -> M(Model)
  - template:字符串 （页面） -> V (View)
  - methods: 对象 (功能)

#### vue中常用的v-指令
* 常用指令
    + 双向数据绑定 v-model="变量名" (变量与页面的关系)
      * 必须要在data中声明(页面影响内存的必须)
      * 在methods中通过this.xxx获取到页面的value值
      * 在template中直接使用xxx获取页面的value值
    + v-if v-else 必须邻居、是插入与移除的故事
    + v-show 是隐藏与显示的故事
    + v-text 双标签、就是元素的innerText
    + v-html 双标签、就是元素的innerHTML
    + `v-for="(ele,index) in arr" :key="index"`
    + `v-for="(value,key,index) in obj" :key="index"`
    + v-on:原生事件="表达式或函数" 
      * 简写->    @原生事件
    + v-bind:属性="表达式或函数"
      * 简写->    :属性
* template只能有一个根节点
* v-for 单个参数可以省略括号，其他的要加括号
* template中使用的变量。data一定要声明
  - template中使用的函数。methods一定要声明

#### 特殊属性key
* vue中列表的输出，都会写上:key="变量值"
* vue默认会根据自己的算法去标识DOM元素与js内存元素之间的位置关系
  - 如果不给key，vue计算浪费性能
  - 如果给定key, vue不会计算了,提升性能
* 列表中的双向数据绑定,DOM元素的值与js内存元素之间的值的关系

#### 类名实现列表样式
* class 是可变的
* class 接收的值，最终会被转换为 `样式1 样式2 样式3`
  - 一个样式
    + 最终返回字符串
  - 多个样式
    + 1:可以是对象{样式1:true,样式2:true}
    + 2:字符串 `样式1 样式2 样式3`
