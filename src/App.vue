<template>
<div id="app">
  <div>
  <Criador/>
  </div>
</div>
</template>

<script>
import Criador from './components/Criador.vue'

export default {
  name: 'App',
  components: {
    Criador
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

.img{
  text-align: left;
}

.img img{
    width: 40px;
    margin-top: -60px
}
</style>
