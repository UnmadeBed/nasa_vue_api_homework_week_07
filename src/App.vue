

<template lang="html">
  <div>
    <h1>NASA Photo of The Day</h1>
    <!-- Move this into a seperate image view component -->
    <!-- <img :src="nasa.url" :alt="nasa.url"> MOVED -->
    <input type="date" v-model="search"/>
    <image-view :nasa="nasa" ></image-view>

  </div>

</template>

<script>
import ImageView from "./components/ImageView.vue"
export default {
  data(){
    return {
      nasa: [],
      search:""
    }
  },
  mounted (){
    fetch('https://api.nasa.gov/planetary/apod?api_key=C0ehDJAti1cLdlnjQciOknJg4WMAeOBqcpOL1G4a')
    .then(res => res.json())
    .then(nasa => this.nasa = nasa)
  },
  components: {
    "image-view": ImageView
  }

}
</script>

<style lang="css" scoped>
</style>
