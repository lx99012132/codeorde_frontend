<template>
  <div id="app">
    <button @click="loadData()">加载API服务器上的数据</button>
    <div>{{userList}}</div>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  data: function () {
    return {
      userList: [],
    };
  },
  methods:{
    loadData(){
      let url='http://codeorder.applinzi.com/user';
      axios.get(url).then((res)=>{
        this.userList=res.data;
      });
    }
  }
};
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
