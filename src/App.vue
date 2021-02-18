<template>
  <div id="app">
    <homepage />
    <contactus/>
  </div>
</template>

<script>
import Vue from 'vue'
import { BootstrapVue } from 'bootstrap-vue'
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import homepage from './components/homepage.vue'
import contactus from './components/contactus';

Vue.use(BootstrapVue)

export default {
  name: 'App',
  components: {
    homepage,
    contactus,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #c9d9e9;
  background-color: rgb(144, 155, 223);
  margin-top: 0px;
}
</style>
