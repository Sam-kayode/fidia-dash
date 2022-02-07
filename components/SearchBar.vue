<template>
  <div class="search-container">
    <b-icon icon="search" class="search-icon"></b-icon>
    <input type="text" placeholder="Search" class="search" />
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
}
</script>

<style lang="scss" scoped>
.search-container {
  width: 100%;
  position: relative;
}
.search {
  width: 100%;
  height: 44px;
  border: 1px solid #d0d5dd;
  box-sizing: border-box;
  box-shadow: 0px 1px 2px rgba(16, 24, 40, 0.05);
  border-radius: 8px;
  outline: none;
  padding: 10px 42px;
}

.search-icon {
  position: absolute;
  width:15px;
  height:15px;
  left: 16px;
  top: 15px;
  z-index: 44444;
  color:#667085;
}
</style>
