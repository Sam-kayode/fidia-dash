<template>
  <div class="">
    <nuxt />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({})
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@200;300;400;500;600;700&display=swap');

* {
  box-sizing: border-box !important;
  margin: 0;
  padding: 0;
}

html {
  width: 100vw;
}

body {
  font-family: Inter, sans-serif;
  font-size: 1rem;
  line-height: 1.6;
  overflow-x: hidden;
}
</style>
