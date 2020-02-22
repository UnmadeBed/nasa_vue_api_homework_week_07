<template lang="html">
  <div>
    <img :src="nasa.url" :alt="nasa.url">
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
