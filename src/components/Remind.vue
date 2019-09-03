<template>
  <div class="bar-container">
    <div class="circle-panel">
      <div class="small-circle"></div>
      <span class="font-middle">待销户提醒</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Remind',
  methods: {
    
  },
  mounted() {
 
  }
}
</script>

<style scoped>
  .bar-container {
    width: 25%;
    height: 350px;
    border: 1px solid #102447;
    border-radius: 4px;
    margin-top: 20px;
    position: absolute;
    right: 40px;
    bottom: 35px
  }
  .circle-panel {
    box-sizing: border-box;
    color: #fff;
    padding: 20px 20px 0;
    font-size: 12px;
  } 
  .small-circle {
    display: inline-block;
    width: 5px;
    height: 5px;
    border-radius: 50%;
    background: linear-gradient(to right, #962e79,#23183a);
    margin-right: 5px;
  }
  .font-middle {
    vertical-align: middle;
  }
</style>
