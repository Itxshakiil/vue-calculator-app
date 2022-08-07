<template>
  <div id="app">
    <calcultor />
    <a href="https://github.com/itxshakil/vue-calculator-app">View Code</a>
    <a class="float-btn" href="mailto:itxshakil@gmail.com?Subject=An%20issue%20found%20in%20Vue%Calculator%20App">Report an Issue</a>
  </div>
</template>

<script>
import Calculator from './components/Calculator.vue'

export default {
  name: 'app',
  components: {
    Calculator
  }
}
</script>

<style>
*{
  box-sizing:border-box;
}
body{
  background:#099;
  position:relative;
}
a{
  display:inline-block;
  margin-top:10px;
  text-decoration:none;
  color:#ddd;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  box-sizing: border-box;
}
.float-btn{
  padding:.4rem;
  position:fixed;
  right:0;
  bottom:0;
}
</style>
