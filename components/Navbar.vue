<template>
  <div class="navbar">
    <div class="right-nav">
      <div class="logo align-self-center">
        <img src="/logo.svg" alt="" />
      </div>
      <ul class="m-0 p-0 nav-links d-none d-lg-flex">
        <li v-for="(link, index) in navLinks" :key="index" class="nav-link">
          {{ link }}
        </li>
      </ul>
    </div>
    <div class="left-nav d-none d-lg-flex">
      <Button icon="/lightning.svg" button-content="Upgrade now" />
      <div class="icons">
        <span class="setting-icon icon"><img src="/setting.svg" alt="" /></span
        ><span class="alert-icon icon"> <img src="/alert.svg" alt="" /></span>
      </div>
      <img src="/avatar.svg" alt="" />
    </div>
<img src="/hamburger.svg" alt="" class="hamburger d-lg-none">
  </div>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return {
      navLinks: [
        'Home',
        'Dashboard',
        'Projects',
        'Tasks',
        'Reporting',
        'Users',
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
  align-items: center;
  padding: 16px 112px;
  border-bottom: 1px solid #eaecf0;
}
.nav-links {
  display: flex;
}

.right-nav,
.left-nav {
  display: flex;
  align-items: center;
  height:100%;
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

.hamburger{
  width:40px;
  height:40px;
}

@include mobile{
.navbar {
  height: 64px;
  padding: 0px 8px 0 16px;
}
}
</style>
