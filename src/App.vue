<template>
<div class="container">
    <Header :logo="logo" />
</div>
</template>

<script>
import Header from './components/MyHeader.vue'
export default {
  name: 'App',
  components:{ Header},
  data(){
    return{
      logo: "AmizingSneakrs"
    }
  },
}
</script>

<style>
body{
  margin: 0;
  padding: 0;
  overflow: hidden;
}
#app {
  font-family: 'HypeSans','Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.container{
  width: 100vw;
  height: 100vh;
}

.connect_btn{
  padding: 20px;
  width: 230px;
  height: 30px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 16px;
  font-weight: 700;
  font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.connect_btn > img{
  width: 30px;
  height: 30px;
  margin-right: 10px;
}
</style>
