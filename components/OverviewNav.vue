<template>
  <div class="navbar d-none d-lg-flex">
    <div class="right-nav">
      <ul class="m-0 p-0 nav-links">
        <li v-for="(link, index) in navLinks" :key="index" class="nav-link">
          {{ link }}
        </li>
      </ul>
    </div>
    <div class="left-nav">
      <SearchBar/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return {
      navLinks: [
        'Overview',
        'Notifications',
        'Analytics',
        'Saved reports',
        'Trade history',
        'Saved reports',
      ],
    }
  },
}
</script>

<style scoped lang="scss">
.navbar {
  height: 72px;
  display: flex;
  justify-content: space-between;
  padding:16px 112px;
  border-bottom: 1px solid  #EAECF0;
}
.nav-links {
  display: flex;
}

.right-nav,
.left-nav {
  display: flex;
  align-items: center;
}

.left-nav {
  width: 320px;
}

.nav-link {
  font-family: 'Inter', sans-serif;
  padding: 8px 12px;
  text-align: center;
  font-size: 16px;
  font-style: normal;
  font-weight: 500;
  line-height: 24px;
  letter-spacing: 0em;
  color: #344054;
  cursor: pointer;
}

.logo {
  margin-right: 29px;
}

.icon {
  width: 40px;
  height: 40px;
  padding: 11px;
}

.alert-icon {
  margin-left: 4px;
}

.icons {
  margin: 0px 16px;
}
</style>
