<template>
  <div class="img-contain">
    <img
      v-for="(member, index) in users"
      :key="member"
      class="m1"
      :src="'/users/' + user + '.svg'"
      :style="{ right: index * 23 + 'px' }"
    />
  </div>
</template>

<script>
export default {
  name: 'Members',
  props: {
    users: { type: Array, default: Array },
  },
  data() {
    return {}
  },
}
</script>

<style lang="scss" scoped>
.m1 {
  position: relative;
  width: 24px;
  height: 24px;
}

.img-contain {
  width: 110px;
}
</style>
