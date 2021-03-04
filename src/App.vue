<template>
  <div id="app"></div>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  <Todolist />
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Todolist from './components/Todolist.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Todolist,
  },
}
</script>

<style>
#app {
  margin-top: 60px;
  font-size: 1.5rem;
}
</style>
