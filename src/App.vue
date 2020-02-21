

<template lang="html">
  <div>
    <h1>NASA Photo of The Day</h1>
    <!-- Move this into a seperate image view component -->
    <img :src="nasa.url" :alt="nasa.url">

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
