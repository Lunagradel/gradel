<template>
  <div class="nav-bar">
    <router-link to="/">
      <p class="header">LUNA GRÄDEL</p>
    </router-link>
    <div v-on:click="toggleMenu" class="burger-menu">
      <div v-for="(n, index) in 3" :key="index" class="burger-line">
      </div>
    </div>
    <burgerMenu v-if="showMenu" @closeMenu="toggleMenu"/>
  </div>
</template>

<script>
import burgerMenu from './Menu.vue'

export default {
  name: 'navBar',
  data(){
    return{
      showMenu: false
    }
  },
  methods: {
    toggleMenu() {
      this.showMenu = !this.showMenu;
    }
  },
  components: {
    burgerMenu
  }
}
</script>
