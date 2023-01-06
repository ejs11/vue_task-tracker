<template>
  <div class="container">
    <Header/>
  </div>
</template>

<script>
import Header from './components/Header.vue'

export default {
  name: 'App',
  components: {
    Header
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
.container {
  width: 450px;
  height: auto;
  margin: auto;
  padding: 20px 10px;
  outline: none;
  border: none;
  box-sizing: border-box;
  box-shadow: 3px 2px 3px 2px gray;
}
</style>
