<template>
  <div class="progress">
    <div class="progress-value" :style="{ width: width + '%' }"></div>
  </div>
</template>

<script>
export default {
  name: 'ProgressBar',
  props: {
    width: {
      type: Number,
      default: null,
    },
  },
  data() {
    return {}
  },
}
</script>

<style>
.progress {
  background: #f9f5ff;
  justify-content: flex-start;
  border-radius: 4px;
  align-items: center;
  position: relative;
  display: flex;
  height: 8px;
  max-width: 88px;
}

.progress-value {
  box-shadow: 0 10px 40px -10px #fff;
  border-radius: 4px;
  background: #7f56d9;
  height: 8px;
}
</style>
