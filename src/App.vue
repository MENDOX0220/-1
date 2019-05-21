<template>
  <div id="app">
    <Ani :title="i.title" :path="i.path" v-for="i in aniList.complete" :key="i"></Ani>
  </div>
</template>

<script>
import axios from 'axios'
import Ani from './components/Ani'

export default {  
  name: "App",
  components:{
    Ani
  },
  data(){
    return{
      aniList : []
  }
},
  created(){
    this.getAniList()
},
  methods: {
    getAniList(){
      axios.get("http://ani.sunrin.life:3030/getAniList")
      .then(data=>{
        this.aniList = data.data
      })
    }
}
}
</script>

<style>
#app{
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  text-align: center;
}
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
