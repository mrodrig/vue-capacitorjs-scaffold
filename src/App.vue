<template>
  <div id="container">
    <navigation-bar />

    <router-view />

    <navigation-tab-bar :navItems="navItems" />
  </div>
</template>

<script>
import { shallowRef } from 'vue';
import HomeIcon from 'vue-material-design-icons/Home.vue';
import NewsIcon from 'vue-material-design-icons/NewspaperVariant.vue';
import CalendarIcon from 'vue-material-design-icons/Calendar.vue';
import NavigationBar from '@/components/NavigationBar.vue';
import NavigationTabBar from '@/components/NavigationTabBar.vue';

export default {
  name: 'app',
  components: {
    NavigationBar,
    NavigationTabBar,
  },
  data() {
    return {
      navItems: [
        { title: 'Home', route: '/', image: shallowRef(HomeIcon) },
        { title: 'News', route: '/news', image: shallowRef(NewsIcon) },
        { title: 'Events', route: '/events', image: shallowRef(CalendarIcon) },
      ],
    };
  },
};
</script>

<style lang="less">
@import "./less/base.less";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100%;
  color: @fontColor;
}

#container {
  display: flex;
  flex-direction: column;
  flex-wrap: nowrap;
  justify-content: space-between;
  align-items: space-between;
  height: 100%;
}
</style>
