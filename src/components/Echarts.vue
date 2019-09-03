<template>
    <div class="parent-container">
      <div class="title">掌中宝人力资源系统</div>
        <PieEcharts/>
        <LineEcharts/>
        <BarEcharts/>
        <Remind/>
    </div>
</template>

<script>
import PieEcharts from './Pie'
import LineEcharts from './Line'
import BarEcharts from './Bar'
import Remind from './Remind'

export default {
  name: 'Echarts',
  methods: {
  
  },
  components: {
    PieEcharts,
    LineEcharts,
    BarEcharts,
    Remind
  },
  mounted() {

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .parent-container {
    width: 100%;
    height: 100%;
    background: #0a112b;
    padding: 0 40px;
  }
  .title {
    text-align: center;
    color: #fff;
    font-size: 24px;
    font-weight: bold;
  }
</style>
