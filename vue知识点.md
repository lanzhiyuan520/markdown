1.搭建环境使用vue-cli创建一个项目

```
npm install --global vue-cli   //全局安装vue-cli
vue init webpack app  //创建一个app的项目(app为项目名称自己定义)
cd app  //进入项目
npm install  //安装依赖
npm run dev  //运行项目
npm run build  //打包项目
```

2.vue的声明周期

```vue
beforeCreate  //实例创建前
created  //实例创建后
beforeMount  //挂载前
mounted  //挂载后
beforeUpdate  //更新前
updated  //更新后
beforeDestroy  //销毁前
destroyed  //销毁后
```

3.条件渲染

```vue
v-if && v-else  //只有v-if表达式成立才会渲染v-if否则渲染v-else
<p v-if='true'>显示</p>
<p v-else>不显示</p>

v-if && v-else-if && v-else  //可以连续使用v-else-if，v-else必须放在最后
<p v-if='type=="a"'>a</p>
<p v-else-if='type=="b"'>b</p>
<p v-else='type=="c"'>c</p>

v-show  //v-show和v-if可以实现同样的效果，但是不同的是v-if不会渲染dom元素，v-show会渲染元素，增加了			display:none属性
<p v-show="true">显示</p>
```

4.列表渲染

```vue
<li v-for="(item,index) in arr" :key="index">{{item.id}}</li>
arr : 要循环的数据(数组)
item : 当前循环的元素
index : 当前循环的下标
key : 每一个元素的标识
```

5.事件修饰符

```vue
<!-- 阻止单击事件继续传播 -->
<a v-on:click.stop="doThis"></a>

<!-- 提交事件不再重载页面 -->
<form v-on:submit.prevent="onSubmit"></form>

<!-- 修饰符可以串联 -->
<a v-on:click.stop.prevent="doThat"></a>

<!-- 只有修饰符 -->
<form v-on:submit.prevent></form>

<!-- 添加事件监听器时使用事件捕获模式 -->
<!-- 即元素自身触发的事件先在此处理，然后才交由内部元素进行处理 -->
<div v-on:click.capture="doThis">...</div>

<!-- 只当在 event.target 是当前元素自身时触发处理函数 -->
<!-- 即事件不是从内部元素触发的 -->
<div v-on:click.self="doThat">...</div>
```

6.

























2.vue路由懒加载

```vue
component : resolve => require(['path'],resolve)
path : 路径(../components/js.vue)
```