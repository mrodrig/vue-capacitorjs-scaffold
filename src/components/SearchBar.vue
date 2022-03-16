<template>
  <div id="search-bar">
    <input type="text" 
            class="search"
            v-model="searchTerm"
            @keypress="triggerSearch" />
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
  props: {
    navItems: Array,
    default: () => [],
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


</style>
