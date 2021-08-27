# vue-cli

vue-cli 是 Vue.js 开发的标准工具。它简化了程序员基于 webpack 创建工程化的 Vue 项目的过程。



https://cli.vuejs.org/zh/





vue-cli 是 npm 上的一个全局包，使用 npm install 命令，即可方便的把它安装到自己的电脑上：

`npm install -g @vue/cli`



基于 vue-cli 快速生成工程化的 Vue 项目：

`vue create 项目的名称`



**4. vue 项目的运行流程**

在工程化的项目中，vue 要做的事情很单纯：通过 main.js 把 App.vue 渲染到 index.html 的指定区域中。

其中：

① App.vue 用来编写待渲染的模板结构

② index.html 中需要预留一个 el 区域

③ main.js 把 App.vue 渲染到了 index.html 所预留的区域中



}).$mount('#app') 和 使用 el: "#app"作用完全一样





# **vue 组件**

组件化开发指的是：根据封装的思想，把页面上可重用的 UI 结构封装为组件，从而方便项目的开发和维护



vue 是一个支持组件化开发的前端框架。

vue 中规定：组件的后缀名是 .vue。之前接触到的 App.vue 文件本质上就是一个 vue 的组件。



**3. vue 组件的三个组成部分**

每个 .vue 组件都由 3 部分构成，分别是：

- template -> 组件的模板结构

- script -> 组件的 JavaScript 行为

- style -> 组件的样式

其中，每个组件中必须包含 template 模板结构，而 script 行为和 style 样式是可选的组成部分。

![image-20210827093444300](README.assets/image-20210827093444300.png)



![image-20210827093524785](README.assets/image-20210827093524785.png)

![image-20210827093543089](README.assets/image-20210827093543089.png)

![image-20210827093600147](README.assets/image-20210827093600147.png)



![image-20210827093615269](README.assets/image-20210827093615269.png)









```js
export default {
  //data数据源
  //注意： 。vue 组件中的data 不能像之前一样，不能指向对象
  //注意： 组件中的 data 必须是一个函数
  data(){
    //这个 return 出去的{}中，可以定义数据
    return{
      username: 'admin'
    }
  },
  methods: {
    changeName(){
      //在组件岁 this 表示当前组件的 实例对象
      this.username = 'zs'
    }
  },
  // 当前组件中的监听器
  watch: {},
  // 当前组件中的计算属性
  computed: {},
  // 当前组件中的过滤器
  filters: {}
}
```



模板结构中只能有一个根元素

```html
  <div id="app">
     <h3>这里是用户自定义的 -------{{ username }}</h3>
    <button @click="changeName">修改用户名</button>
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
```

如果想使用less语法需要声明

```less
<style lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
```

