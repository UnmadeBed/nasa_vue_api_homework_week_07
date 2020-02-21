

<template lang="html">
  <div>
    <h1>NASA Photo of The Day</h1>
    <p>{{ nasa }}</p>

  </div>

</template>

<script>
export default {
  data(){
    return {
      nasa: []
    }
  },
  mounted (){
    fetch('https://api.nasa.gov/planetary/apod?api_key=C0ehDJAti1cLdlnjQciOknJg4WMAeOBqcpOL1G4a')
    .then(res => res.json())
    .then(nasa => this.nasa = nasa)
  }

}
</script>

<style lang="css" scoped>
</style>






<!-- <template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
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
</style> -->
