<template>
  <button
    class="button"
    :style="{ color: activeColor, background: background }"
    :class="{ 'no-border': border }"
  >
    <img :src="icon" alt="" class="icon" />
    {{ buttonContent }}
  </button>
</template>

<script>
export default {
  props: {
    activeColor: { type: String, default: '#344054' },
    background: { type: String, default: '' },
    buttonContent: {
      type: String,
      default: '',
    },
    icon: {
      type: String,
      default: '',
    },
    border: {
      type: Boolean,
      default: false,
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
  border: 1px solid #d0d5dd;
  box-shadow: 0px 1px 2px rgba(16, 24, 40, 0.05);
  border-radius: 8px;

  .icon {
    width: 16px;
    margin-right: 10.5px;
  }

  &::placeholder{
    
  }
}

.no-border {
  border: none !important;
}
</style>
