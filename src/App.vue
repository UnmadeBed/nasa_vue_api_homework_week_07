<template lang="html">
  <div>
    <h1>NASA Photo of The Day</h1>
    <!-- Move this into a seperate image view component -->
    <!-- <img :src="nasa.url" :alt="nasa.url"> MOVED -->
    <input v-model="selectedDate" type="date">
    <button @click="callApi">Get new image</button>
    <image-view :nasa="nasa" ></image-view>
  </div>

</template>

<script>
import ImageView from './components/ImageView.vue'
export default {
  data() {
    return {
      nasa:[],
      selectedDate: '2020-02-20'
    };
  },
  created() {
    this.makeAPICall();
  },
  methods: {
    makeAPICall() {
      fetch('https://api.nasa.gov/planetary/apod?api_key=C0ehDJAti1cLdlnjQciOknJg4WMAeOBqcpOL1G4a')
      .then(res => res.json())
      .then(nasa => this.nasa = nasa)
    },
    callApi(selectedDate) {
      fetch('https://api.nasa.gov/planetary/apod?api_key=C0ehDJAti1cLdlnjQciOknJg4WMAeOBqcpOL1G4a&date=' + this.selectedDate + '')
      .then( res => res.json())
      .then(nasa => this.nasa = nasa)

    }
  },
  components: {
    "image-view": ImageView
  }
};
</script>

<style lang="css" scoped>
</style>

methods: {
     getResult(query) {
       axios.get('https://images-api.nasa.gov/search?q=' + query + '&media_type=image').then( response => {
           console.log(response.data.collection.items);
           this.results = response.data.collection.items;


<!-- callApi() will want to use this.selectedDate -->
