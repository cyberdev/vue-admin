<template>
  <div class="sidebar-logo-container" :class="{'collapse':collapse}">
    <router-link v-if="!collapse" key="expand" class="sidebar-logo-link" to="/">
      <img v-if="logo" :src="logo" class="sidebar-logo">
      <h1 class="sidebar-title">{{ title }} </h1>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'SidebarLogo',
  props: {
    collapse: {
      type: Boolean,
      required: true
    }
  },
  data() {
    return {
      title: 'Vue Element Admin',
      logo: false
    }
  }
}
</script>

<style lang="scss" scoped>
.sidebar-logo-container {
  position: absolute;
  height: 50px;
  line-height: 50px;
  overflow: hidden;
  padding: 0 20px;

  & .sidebar-logo-link {
    height: 100%;
    width: 100%;

    & .sidebar-logo {
      width: 32px;
      height: 32px;
      vertical-align: middle;
      margin-right: 12px;
    }

    & .sidebar-title {
      display: inline-block;
      margin: 0;
      color: #fff;
      font-weight: 600;
      line-height: 50px;
      font-size: 14px;
      font-family: Avenir, Helvetica Neue, Arial, Helvetica, sans-serif;
      vertical-align: middle;
    }
  }

  &.collapse {
    .sidebar-logo {
      margin-right: 0px;
    }
  }
}
</style>
