<template>
  <div class="img-contain">
    <img
      v-for="(user, index) in users.slice(0, 5)"
      :key="index"
      class="m1"
      :src="'/users/' + user + '.png'"
      :style="{ left: index * -8 + 'px' }"
    />
    <div
      v-if="users.length > 5"
      class="extras d-inline-flex align-items-center justify-content-center"
      :style="{ left: 6 * -7.5 + 'px' }"
    >
      +{{ users.length - 5 }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'Users',
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

.extras {
  font-family: Inter;
  font-size: 12px;
  font-style: normal;
  font-weight: 500;
  line-height: 18px;
  letter-spacing: 0em;
  text-align: center;
  color: #7f56d9;
  width: 24px;
  height: 24px;
  border: 2px solid #ffffff;
  border-radius: 200px;
  background: #f9f5ff;
  position: relative;
  padding-top: 2px;
}
</style>
