<template lang="html">
  <div>
    <img :src="nasa.url" :alt="nasa.url">
    <h2>Date: {{ nasa.date }}</h2>
    <h1>Title: {{ nasa.title }}</h1>
    <p>Explanation: {{ nasa.explanation }}</p>
    <p>HDURL: {{ nasa.hdurl }}</p>
    <p>COPYRIGHT: {{ nasa.copyright }}</p>
  </div>

</template>

<script>

export default {
  name: 'image-view',
  props: ['nasa']
}
</script>

<style lang="css" scoped>
</style>
