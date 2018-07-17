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
        anchors: ['default', 'info', 'experience', 'works', 'skill', 'contact'],
        sectionsColor: ['#87b0a5', '#109085', '#945c4c', '#4b85a0', '#4d5e8f', '#a29971']
      }
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
  }
}
</script>

<style>
</style>
