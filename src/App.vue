<script>
import PageTitle from './components/PageTitle.vue';
import AppNav from './components/AppNav.vue';
import AppMain from './components/AppMain.vue';

export default {
  components: {
    PageTitle,
    AppNav,
    AppMain,
  }
}
</script>

<template>
  <div>
    <PageTitle/>
    <AppNav />
    <AppMain />
  </div>
</template>

<style lang="scss" scoped>

@import "./style/global.scss";

</style>
