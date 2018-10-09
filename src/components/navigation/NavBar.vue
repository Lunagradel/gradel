<template>
  <div class="nav-bar">
    <p class="header">LUNA GRÄDEL</p>
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
    toggleMenu: function(){
      this.showMenu = !this.showMenu;
    }
  },
  components: {
    burgerMenu
  }
}
</script>
