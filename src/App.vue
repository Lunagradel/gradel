<template>
  <div id="app">
    <!-- <div id="nav-bar">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div> -->
    <NavBar/>
    <router-view/>
  </div>
</template>

<script>
import NavBar from './components/navigation/NavBar.vue'

export default {
  name: 'App',
  components: {
    NavBar
  }
}

</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Montserrat:800');
@import '@/css/style.scss';
</style>
