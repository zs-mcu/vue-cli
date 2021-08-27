<template>
  <div id="app">
     <h3>这里是用户自定义的 -------{{ username }}</h3>
    <button @click="changeName">修改用户名</button>
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

//默认导出： 固定写法！
export default {
  name: 'App',
  components: {
    HelloWorld
  },
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
</script>

<style lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
