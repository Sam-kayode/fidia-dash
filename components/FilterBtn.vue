<template>
  <button class="button">
    {{ buttonContent }}
    <img src="/x.svg" alt="" class="icon" />
  </button>
</template>

<script>
export default {
  props: {
    buttonContent: {
      type: String,
      default: '',
    },
    icon: {
      type: String,
      default: '',
    },
  },
}
</script>

<style scoped lang="scss">
.button {
  padding: 10px 16px;
  border: none;
  height: 40px;
  font-family: Inter, sans-serif;
  font-size: 14px;
  font-style: normal;
  font-weight: 500;
  line-height: 20px;
  letter-spacing: 0em;
  background: #ffffff;
  border: none;
  box-shadow: 0px 1px 2px rgba(16, 24, 40, 0.05);
  border-radius: 8px;
  color: #6941c6;
  background: #f9f5ff;
  margin-right: 12px;
  .icon {
    width: 10px;
    margin-left: 13px;
  }
}

.no-border {
  border: none !important;
}
</style>
