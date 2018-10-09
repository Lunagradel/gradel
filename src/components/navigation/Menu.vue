<template>
  <div class="menu">
    <div class="top-menu">

      <div class="top-menu-point menu-point">
          <p class="header">home</p>
      </div>

      <div class="top-menu-point menu-point" v-on:click="$emit('closeMenu')">
        <p>&#10006;</p>
      </div>
    </div>

    <div class="menu-points">

      <div v-for="(item, index) in menuPoints" :key="index" class="menu-point main-menu-point header">
        <p>{{item}}</p>
      </div>
      
    </div>

  </div>
</template>

<script>
export default {
  name: 'Menu',
  data(){
    return{
      menuPoints: [
        'work',
        'about',
        'cv'
      ]
    }
  }
}
</script>
