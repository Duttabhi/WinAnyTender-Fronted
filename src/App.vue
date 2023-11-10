<template>
  <HeaderSection msg="Header"/>
  <BusinessProfile msg="Business Profile Landing"/>
</template>

<script>
import HeaderSection from './components/HeaderSection.vue'
import BusinessProfile from './components/BusinessProfile.vue'

export default {
  name: 'App',
  components: {
    HeaderSection,
    BusinessProfile
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
}
</style>
