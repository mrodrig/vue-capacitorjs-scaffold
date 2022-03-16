<template>
  <div id="nav-bar">
    <div @click="back" class="side">
      <div v-show="!isHome" id="back-nav" >
        &lt;
      </div>
    </div>

    <h1>
      {{title}}
    </h1>

    <!-- Empty element to center the title -->
    <div class="side" />
  </div>
</template>

<script>
export default {
  name: 'NavBar',
  computed: {
    isHome() {
      return this.$route.path === '/';
    },
    title() {
      return this.$route.name;
    },
  },
  methods: {
    back() {
      window.history.back();
    },
  },
};
</script>

<style scoped lang="less">
@import "../less/base.less";

#nav-bar {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content:  space-between;
  align-items: center;
  align-content: stretch;
  background: @background;

  .side {
    flex: 1;
  }

  #back-nav {
    cursor: pointer;
    padding: 0 1.6em;
  }

  h1 {
    margin-block-start: .3em;
    margin-block-end: .3em;
  }
}
</style>
