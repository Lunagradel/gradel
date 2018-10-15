<template>
  <div :class="['singlework-wrapper', {'go-down': close}]" v-bind:style="{ backgroundColor: chosen.backgroundColor }">
    <div class="sw-top" v-bind:style="{ backgroundImage: 'url(' + require('./../../assets/' + chosen.images.header) + ')' }">
      <div class="close" :style="{color: chosen.btnColor}" v-on:click="handleClose">&#10006;</div>
      <div class="gradient-layer" v-bind:style="{ background: ['linear-gradient(to bottom, transparent 60%,'+ chosen.backgroundColor +' 100%)', '-webkit-linear-gradient(top, transparent 60%, '+chosen.backgroundColor+' 100%)', '-moz-linear-gradient(top, transparent 60%, '+chosen.backgroundColor+' 100%)']}"></div>
    </div>
    <div class="sw-content" v-bind:style="{ backgroundColor: chosen.backgroundColor }">
      <div class="sw-images">
        <div class="sw-img">
          <img :src="require('./../../assets/'+ chosen.images.imgOne)" alt="">
        </div>
        <div class="sw-img">
          <img :src="require('./../../assets/'+ chosen.images.imgTwo)" alt="">
        </div>
      </div>
      <div class="sw-text" :style="{ color: chosen.textColor }">
        <span v-html="chosen.text"></span>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'SingleWork',
  props: ['chosen'],
  data: () => ({
    close: false
  }),
  methods: {
    handleClose(){
      this.close = true;
      this.$emit('startAnimate');
      let self = this;
      setTimeout(function(){
        self.$emit('closeSingle');
      }, 900);
    }
  }
}
</script>
