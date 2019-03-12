1.搭建环境使用vue-cli创建一个项目

```
npm install --global vue-cli   //全局安装vue-cli
vue init webpack app  //创建一个app的项目(app为项目名称自己定义)
cd app  //进入项目
npm install  //安装依赖
npm run dev  //运行项目
npm run build  //打包项目
```



2.vue路由懒加载

```vue
component : resolve => require(['path'],resolve)
path : 路径(../components/js.vue)
```