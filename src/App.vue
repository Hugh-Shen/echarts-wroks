<template>
  <div id="app">
      <echarts />
  </div>
</template>

<script>
import Echarts from './components/Echarts.vue'
import './utils/base.css'

export default {
  name: 'app',
  components: {
    Echarts
  }
}
</script>

<style>
 html,body {
   padding: 0;
   margin: 0;
   width: 100%;
   height: 100%
 }
 body {
   height:100%;
 }
 
 #app {
   width: 100%;
   height: 100%
 }
</style>
