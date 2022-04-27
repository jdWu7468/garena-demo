<template>
  <div>
      <h2>Garena-demo</h2>
      <h3>姓名：{{obj.name}}</h3>
      <h3>面试日期：2022/04/27</h3>
      <div>

      </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      obj:{}
    }
  },
  methods: {
    
  },
  created(){
    //获取本地json数据
    var xhr=new XMLHttpRequest();
    xhr.open("get","./config.json",false);
    xhr.send()
    var obj=xhr.responseText;
    this.obj=JSON.parse(obj);
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
