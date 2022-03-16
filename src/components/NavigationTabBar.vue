<template>
  <div id="nav-tab-bar">
    <router-link v-for="navItem in navItems" :key="navItem.title" :to="navItem.route">
      <div class="nav-item" :class="{'nav-item-current': navItem.route === $route.path}">
        <component :is="navItem.image" v-if="navItem.image" />

        <div v-if="navItem.title">
          {{navItem.title}}
        </div>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'TabBar',
  props: {
    navItems: {
      type: Array,
      default: () => [],
    },
  },
  methods: {
    isCurrentItem(navItem) {
      console.log(this.$route.path);
      return this.$route.path === navItem.route;
    },
  },
};
</script>

<style scoped lang="less">
@import "../less/base.less";

#nav-tab-bar {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content:  space-evenly;
  align-items: stretch;
  align-content: stretch;
  background: @background;
  padding: .5em;

  a {
    text-decoration: none;
  }

  .nav-item {
    display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
    justify-content: center;
    align-items: center;
    color: @navigationTitles;
  }

  .nav-item-current {
    color: @navigationTitleSelected
  }
}
</style>
