<script>
import AppMain from './components/AppMain.vue';

export default{
  name: 'AppVue',
  components: {
    AppMain,
  },
  data() {
    return {
      
    }
  },

}
</script>

<template>
  <header></header>

  <main>
    <AppMain />
  </main>
</template>

<style lang="scss">
@use 'bootstrap/scss/bootstrap.scss' as *;
@use 'styles/general.scss' as *;

</style>
