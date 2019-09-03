<template>
  <div class="line-container">
    <div class="circle-panel">
      <div class="small-circle"></div>
      <span class="font-middle">新开账户</span>
    </div>
    <div class="handle-btn">
      <span>月</span>
      <span>年</span>
    </div>
    <div id='line-echarts'></div>
  </div>
</template>

<script>
export default {
  name: 'LineEcharts',
  methods: {
    drawLine() {
      let lineChart = this.$echarts.init(document.getElementById('line-echarts'))
      var option = {
            // title: {
            //     text: '新开账户',
            //     textStyle:{
            //       color: '#fff',
            //       fontSize: 12,
            //       fontWeight: 100
            //     },
            //     left: 'left',
            //     top: 'top'
            // },
            tooltip: {
            },
            legend: {
                data:['收入', '支出'],
                left: 'center',
                bottom: '5%',
                icon: 'rect', 
                itemWidth: 15,
                itemHeight: 3,
                textStyle: {
                  color: '#fff'
                }
            },
            xAxis: {
                data: ["1月","2月","3月","4月","5月"],
                axisLabel: {
                  show: true,
                  textStyle: {
                    color: '#fff',
                  }
                },
                axisLine: {
                  show: false
                },
                axisTick: {
                  show: false
                },
                splitLine: {
                  show: false
                }
            },
            yAxis: {
              type: 'value',
              nameTextStyle: {
                color: '#fff'
              },
              axisLine: {
                show: false,
                lineStyle: {
                  color: '#fff'
                }
              },
              axisTick: {
                show: false
              },
              splitLine: {
                show: false
              }
            },
            series: [
              {
                name: '收入',
                type: 'line',
                data: [5, 20, 36, 10, 10, 20],
                itemStyle: {
                    color: '#e53aa4'
                },
                smooth: true
              },
              {
                name: '支出',
                type: 'line',
                data: [11, 50, 26, 52, 45, 86],
                itemStyle:{
                    color: '#449afd'
                },
                smooth: true
              }
            ]
        };
      lineChart.setOption(option)
    }
  },
  mounted() {
    this.drawLine();
  }
}
</script>

<style scoped>
  .line-container {
    position: absolute;
    right: 40px;
    top: 40px;
    width: 25%;
    height: 300px;
    border: 1px solid #102447;
    border-radius: 4px;
    padding: 20px 20px 0;
    box-sizing: border-box;
  }
  .circle-panel {
    width: 60%;
    box-sizing: border-box;
    color: #fff;
    padding: 5px;
    font-size: 12px;
    display: inline-block;
    position: absolute;
    z-index: 99;
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
  .handle-btn {
    width: 90px;
    height: 25px;
    line-height: 25px;
    border: 1px solid #265895;
    border-radius: 6px;
    position: absolute;
    right: 30px;
    top: 20px;
    color: #265895;
    z-index: 99;
    box-sizing: border-box;
    overflow: hidden;
    font-size: 0px
  }
  .handle-btn > span {
    display: inline-block;
    font-size: 16px;
    width: 50%;
    height: 100%;
    text-align: center;
  }
  .handle-btn > span:first-child {
    background: #275795;
    color: #222
  }
  #line-echarts {
    width: 100%;
    height: 100%;
  }
</style>
