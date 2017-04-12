<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  .menuNav{
    position:fixed;
    width:100%;
    top:0;
    z-index:1000
  }
  .container{
    margin-top:60px;
  }
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

a {
  color: #42b983;
}
</style>
<template>
  <div id="app">
  <el-menu theme="dark" :default-active="activeIndex" class="menuNav" mode="horizontal" @select="handleSelect" :router="true">
    <el-menu-item index="first" >主页</el-menu-item>
    <el-submenu index="2">
      <template slot="title">我的工作台</template>
      <el-menu-item index="2-1">选项1</el-menu-item>
      <el-menu-item index="2-2">选项2</el-menu-item>
      <el-menu-item index="2-3">选项3</el-menu-item>
    </el-submenu>
    <el-menu-item index="second">订单管理</el-menu-item>
  </el-menu>
    <section class="container">
      <!-- <img src="./assets/logo.png">
      <h1>{{ msg }}</h1>
      <ul>
          <li><router-link to="/first">点我跳转到第一页</router-link></li>
          <li><router-link to="/second">点我跳转到第二页</router-link></li>
        </ul> -->
        hello vue，now you can go anywhere~
      <router-view class="view"></router-view>
    </section>
    
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      activeIndex: '1',
        activeIndex2: '1',
      msg: 'Welcome to Your Vue.js Appl'
    }
  },
  methods: {
      handleSelect(key, keyPath) {
        console.log(key, keyPath);
      }
    }
}
</script>


