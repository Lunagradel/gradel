<template>
  <div class="work-wrapper page-wrapper">
    <div class="header-container">
      <p :class="['header page-title', {remove: animate, add: !animate}]">WORK</p>
      <p :class="['header work-title', {add: animate, remove: !animate}]" v-if="showSingleWork">{{chosenWork.thumbName}}</p>
    </div>
    <div class="work-container">
      <!-- <div v-for="(item, index) in workData" :key="index" :class="['work-element', {enlarge: index == selected, test: index != selected && selected != null }]" v-on:click="handleClick(index)"> -->
      <div :class="['work-elements', {remove: animate}]">
        <div v-for="(item, index) in workData" :key="index" class="work-element" v-on:click="handleClick(index)" v-bind:style="{ backgroundImage: 'url(' + require('./../assets/' + item.images.header) + ')' }">
          <div class="element-overlay">
          </div>
          <p class="header" :style="{color: item.thumbColor, backgroundColor: item.backgroundColor}">{{item.thumbName}} &#8594;</p>
        </div>
      </div>
      <SingleWork v-if="showSingleWork" v-bind:chosen="chosenWork" @closeSingle="handleShowSW" @startAnimate="animate = false"/>
    </div>

  </div>
</template>

<script>
import workData from './../data/work.js';
import SingleWork from './../components/work/SingleWork.vue';

export default {
  name: 'work',
  data: () => ({
    workData,
    chosenWork: null,
    showSingleWork: false,
    animate: false
  }),
  methods: {
    handleClick(index){
      this.selected = index;
      this.chosenWork = this.workData[index];
      this.animate = true;
      this.handleShowSW();
    },
    handleShowSW(){
      this.showSingleWork = !this.showSingleWork;
    }
  },
  components: {
    SingleWork
  }
}
</script>
