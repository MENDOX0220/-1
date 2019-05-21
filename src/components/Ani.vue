<template>
  <div id="app">
    <div class="box">
      <img :src="'http://ani.sunrin.life:3030'+path+'/img.jpg'">
      <div>{{title}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Ani',
  props: {
    title: String,
    path : String
  }
}
</script>
<style scoped>
  .box{
    position: relative;
    display: inline-block;
    width: 200px;
    height: 300px;
    border: 2px solid black;
    box-sizing: border-box;
  }
  .box >img{
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
  }
  .box >div{
    position: absolute;
    width: 100%;
    height: 100%;
    color: chocolate;
    font-weight: bold;
  }
</style>
