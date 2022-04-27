<template>
  <div>
      <h2>Garena-demo</h2>
      <h3>姓名：{{obj.name}}</h3>
      <h3>面试日期：2022/04/27</h3>
      <image src='./scape.png' class="logo"></image>
      <div class="main">
        <div class="image">图片来不及放进去，优化方案可以使用雪碧图</div>
        <div class="image"></div>
        <div class="image"></div>
        <div class="image"></div>
        <div class="image"></div>
        <div class="image"></div>
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
.main{
  width: 100%;
}
.image{
  background-color: blue;
  float: left;
  margin-right: 10px;
  margin-top: 10px;
}
@keyframes App-logo{
   0%{
     transform: rotate(0deg)
   }
   50%{
     transform: rotate(90deg);
   }
   100%{
     transform: rotate(90deg);
   }
}

@media (perfers-reduced-motion:no-perference){
  .logo{
    animation:App-logo infinite 1s linear;
    animation-duration:1s;
  }
}
/* 电脑 */
@media screen and (min-width:992px){
  .image{
    width:200px;
    height:200px;
  }
}

/* ipad */
@media screen and (min-width:768px) and (max-width:900px) {
  .image{
    width:800px;
    height:200px;
  }
}

/* 手机 */
@media screen and (min-width:480px){
  .image{
    width:600px;
    height:200px;
  }
}
</style>