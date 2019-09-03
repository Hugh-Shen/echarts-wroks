<template>
  <div class="bar-container">
    <div class="circle-panel">
      <div class="small-circle"></div>
      <span class="font-middle">资金分布(银行)</span>
    </div>
    <div id='bar-echarts'></div>
  </div>
</template>

<script>
export default {
  name: 'BarEcharts',
  methods: {
    drawBar() {
      let barChart = this.$echarts.init(document.getElementById('bar-echarts'))
      let option = {
        color: ['#3398DB'],
        tooltip: {
          
        },
        grid: {
          left: '3%',
          right: '4%',
          bottom: '3%',
          containLabel: true
        },
        xAxis: {
            type: 'category',
            data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'],
            nameTextStyle: {
              color: '#fff'
            },
            axisLabel: {
              show: true,
              textStyle: {
                color: '#fff',  //更改坐标轴文字颜色
                fontSize : 8      //更改坐标轴文字大小
              }
            },
            axisLine: {
              lineStyle: {
                color: '#4699ff'
              }
            },
            axisTick: {
              show: false
            },
            splitLine: {
              show: false
            }
        },
        yAxis: {
            type : 'value',
            axisLabel : {
              formatter: function(){
                return "";
              }
            },
            axisLine: {
              lineStyle: {
                color: '#4699ff'
              }
            },
            axisTick: {
              show: false
            },
            splitLine: {
              show: false
            }
          },
        series : [
          {
            name:'中国银行',
            type:'bar',
            barWidth: 30,
            barGap: '30%',
            data:[10, 52, 20, 34, 30, 30, 27],
            itemStyle: {
              color: {
                type: 'linear',
                x: 0,
                y: 0,
                x2: 0,
                y2: 1,
                colorStops: [
                  {offset: 0, color:'#28b1ff'},
                  {offset: 1, color:'#112750'}
                ]
              }
            }
          },
          {
            name:'工商银行',
            type:'bar',
            barWidth: 30,
            barGap: '30%',
            data:[14, 36, 27],
            itemStyle: {
              color: {
                type: 'linear',
                x: 0,
                y: 0,
                x2: 0,
                y2: 1,
                colorStops: [
                  {offset: 0, color:'#e93ea6'},
                  {offset: 1, color:'#42313b'}
                ]
              }
            }
          }
        ]
      }
      barChart.setOption(option)
    }
  },
  mounted() {
    this.drawBar();
  }
}
</script>

<style scoped>
  .bar-container {
    width: 70%;
    height: 200px;
    border: 1px solid #102447;
    border-radius: 4px;
    margin-top: 20px;
    box-sizing: border-box;
  }
  .circle-panel {
    width: 20%;
    box-sizing: border-box;
    color: #fff;
    padding: 20px 20px 0;
    font-size: 12px;
    display: inline-block;
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
  #bar-echarts {
    width: 80%;
    height: 100%;
    display: inline-block;
    float: right;
  }
</style>
