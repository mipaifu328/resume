<template>
  <div id="app">
    <full-page :options="options">
      <div class="section">
        <v-default/>
      </div>
      <div class="section">
        <v-info/>
      </div>
      <div class="section">
        <v-experience/>
      </div>
      <div class="section">
        <v-works/>
      </div>
      <div class="section">
        <v-skill/>
      </div>
      <div class="section">
       <v-contact/>
      </div>
    </full-page>
    <div class="arrow" v-show="isLast"></div>
  </div>
</template>

<script>
import vDefault from './components/vDefault'
import vInfo from './components/vInfo'
import vExperience from './components/vExperience'
import vWorks from './components/vWorks'
import vSkill from './components/vSkill'
import vContact from './components/vContact'

import FullPage from 'vue-fullpage.js/src/FullPage'
import fullPageMixin from 'vue-fullpage.js/src/fullPageMixin'

export default {
  mixins: [fullPageMixin],
  data () {
    return {
      options: {
        navigation: true,
        // anchors: ['default', 'info', 'experience', 'works', 'skill', 'contact'],
        sectionsColor: ['#87b0a5', '#109085', '#945c4c', '#4b85a0', '#4d5e8f', '#a29971'],
        onLeave: this.onLeave
      },
      isLast: true
    }
  },
  components: {
    FullPage,
    vDefault,
    vInfo,
    vExperience,
    vWorks,
    vSkill,
    vContact
  },
  methods: {
    onLeave (index, nextIndex, direction) {
      if (nextIndex === 6) {
        // 最后一个模块
        this.isLast = false
      } else if (index === 6 && direction === 'up') {
        this.isLast = true
      }
    }
  }
}
</script>
<style>
  .arrow{
    position: absolute;
    bottom: 20px;
    width: 20px;
    height: 35px;
    left: 50%;
    z-index: 100;
    background: url(./assets/images/arrow.svg) bottom center no-repeat;
    background-size: contain;
    pointer-events: none;
    transform: translateX(-50%);
    animation: arrowAnimate 1.5s ease-in-out infinite;
  }
  @keyframes arrowAnimate {
    0% {
      bottom: 10px;
      opacity: .8;
    }
    50% {
      bottom: 20px;
      opacity: 1;
    }
    80% {
      bottom: 22px;
      opacity: .4;
    }
    100% {
      bottom: 22px;
      opacity: 0;
    }
  }
</style>
