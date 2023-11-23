<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App" :press="press"/>
    <button @click="clickMe" > Press Me </button>
    <input disabled v-model="press" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data(){
    return{
      press: 1
    }
  },
  components: {
    HelloWorld
  },
  methods: {
    clickMe(){
      let vm = this
      vm.press = vm.press+1
      console.log(vm.press)
    }
  },
  beforeUpdate(){
    console.log("App beforeUpdate called.")
  },
  updated(){
    console.log("App updated called.")
  },
  mounted(){
    console.log("App mounted called.")
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
