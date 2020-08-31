<template>
  <div id="app">

    <!--========================== 組件使用 ==========================-->

    <!-- <HeaderView msg="父組件傳遞值到子組件"></HeaderView> -->
    <HeaderView :msg="title"></HeaderView>
    <img src="./assets/logo.png">
    <!-- <HelloWorld></HelloWorld> -->
    <ListView @myMsg='getData'></ListView>

  </div>
</template>

<script>

// ===========================導入組件==============================

import HelloWorld from './components/HelloWorld'
import HeaderView from './components/Header'
import ListView from './components/List'
// App.vue是父組件，ListView是子組件 組件間通信
// 父組件 --> 子組件 props選項
// 子組件 --> 父組件 自定義事件

export default {
  name: 'app',
  components:{ //========================註冊組件======================
    HelloWorld,
    HeaderView,
    ListView
  },
  data(){
    return{
      title:'Vue入門學習'
    }
  },
  methods:{
    getData(msg){
      console.log("App.vue組件:" + msg);
      this.title = msg;
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
