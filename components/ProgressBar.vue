<template>
  <div class="progress">
    <div class="progress-value"></div>
  </div>
</template>

<script>
export default {}
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
  width: 30%;
}
</style>
