<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

export default{
  name: 'AppVue',
  components: {
    AppHeader,
    AppMain,
  },
  data() {
    return {
      
    }
  },

}
</script>

<template>
  <header>
    <AppHeader />
  </header>

  <main class="container-lg">
    <router-view></router-view>
  </main>

  <!-- <main>
    <AppMain />
  </main> -->
</template>

<style lang="scss">
@use 'bootstrap/scss/bootstrap.scss' as *;
@use 'styles/general.scss' as *;

</style>
