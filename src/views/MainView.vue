<template>
  <div class="main-container-tabs ">
    <div class="tab" v-bind:class="{ active: activeTab == 'start-screen' }">
      <Page1 @changeTab="changeTab"/>
    </div>
    <div class="tab" v-bind:class="{active: activeTab == 'simulation-screen' }">
      <Page2 @changeTab="changeTab" />
    </div>

    <div class="tab" v-bind:class="{active: activeTab == 'explication-one' }">
      <Page3V1 @changeTab="changeTab" />
    </div>

    <div class="tab" v-bind:class="{active: activeTab == 'explication-two'}">
      <Page3V2 @changeTab="changeTab" />
    </div>

    <div class="tab" v-bind:class="{active: activeTab == 'about-me'}">
      <AboutMe @changeTab="changeTab" />
    </div>
  </div>
</template>

<script>
import Page1 from '../components/Page1.vue'
import Page2 from '../components/Page2.vue'
import Page3V1 from '../components/Page3V1.vue'
import Page3V2 from '../components/Page3V2.vue'
import AboutMe from '../components/AboutMe.vue'

export default {
  name: "MainView",

  data() {
    return {
      activeTab: "start-screen",
    }
  },
  components: {
    Page1,
    Page2,
    Page3V1,
    Page3V2,
    AboutMe
  },
  methods: {
    changeTab(tab) {
      this.activeTab = tab;
    },
  }
}

</script>

<style scoped>

.main-container-tabs {
  position: fixed;
  top: 0;
  left: 0;
  height: 100vh;
  width: 100vw;
}

.tab {
  display: none;
  width: 100%;
  height: 100%;
  align-items: center;
  justify-content: center;
  background-color: #252525;
}

.tab>* {
  z-index: 2;
}

.tab.active {
  display: flex;
}
</style>
