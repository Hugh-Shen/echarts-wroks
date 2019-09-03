<template>
  <div class="echarts-box">
    <div class="echarts1-header">
      <!-- <div class="line"></div> -->
      <div class="list-header">
        <p>薪资总量</p>
        <p>
          12000.90
          <span class="header-text">万元</span>
        </p>
      </div>
      <div class="list-header">
        <p>薪资总量</p>
        <p>
          12000.90
          <span class="header-text">万元</span>
        </p>
      </div>
      <div class="list-header">
        <p>薪资总量</p>
        <p>
          12000.90
          <span class="header-text">万元</span>
        </p>
      </div>
      <div class="list-header">
        <p>薪资总量</p>
        <p>
          12000.90
          <span class="header-text">万元</span>
        </p>
      </div>
    </div>
    <div class="circle-panel">
      <div class="small-circle"></div>
      <span class="font-middle">薪资分布单位</span>
    </div>
    <div id="echarts-container"></div>
  </div>
</template>

<script>
export default {
  name: "Pie",
  methods: {
    drawChart() {
      let myChart = this.$echarts.init(
        document.getElementById("echarts-container")
      );
      let option = {
        // title: {
        //   text: ['薪资分布单位'],
        //   textStyle: {
        //     color: '#fff',
        //     fontSize: 12,
        //     fontWeight: 100
        //   }
        // },
        tooltip: {
          trigger: "item"
        },
        legend: {
          left: "center",
          bottom: "10%",
          icon: "circle",
          itemWidth: 10,
          itemHeight: 10,
          textStyle: {
            color: "#fff"
          }
        },
        xAxis: {
          show: false,
          data: []
        },
        yAxis: {
          show: false
        },
        series: [
          {
            name: "销量",
            radius: ["30%", "50%"],
            type: "pie",
            data: [
              {
                value: 50,
                name: "50%",
                label: { color: "#fff" },
                labelLine: { lineStyle: { color: "#fff" } },
                itemStyle: {
                  color: {
                    type: "linear",
                    x: 0,
                    y: 0,
                    x2: 0,
                    y2: 1,
                    colorStops: [
                      { offset: 0, color: "#feaa62" },
                      { offset: 1, color: "#eb47a0" }
                    ]
                  }
                }
              },
              {
                value: 33,
                name: "33%",
                label: { color: "#fff" },
                labelLine: { lineStyle: { color: "#fff" } },
                itemStyle: {
                  color: {
                    type: "linear",
                    x: 0,
                    y: 0,
                    x2: 0,
                    y2: 1,
                    colorStops: [
                      { offset: 0, color: "#2f66f6" },
                      { offset: 1, color: "#6717ce" }
                    ]
                  }
                }
              },
              {
                value: 17,
                name: "17%",
                label: { color: "#fff" },
                labelLine: { lineStyle: { color: "#fff" } },
                itemStyle: {
                  color: {
                    type: "linear",
                    x: 0,
                    y: 0,
                    x2: 0,
                    y2: 1,
                    colorStops: [
                      { offset: 0, color: "#29a9ff" },
                      { offset: 1, color: "#2c8dfe" }
                    ]
                  }
                }
              }
            ]
          }
        ]
      };
      myChart.setOption(option);
    }
  },
  mounted() {
    this.drawChart();
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.echarts-box {
  width: 25%;
  height: 480px;
  box-sizing: border-box;
  border: 1px solid #102447;
  border-radius: 4px;
  padding: 20px 20px 0;
}
.echarts1-header {
  width: 100%;
  height: 100px;
}
.list-header {
  display: inline-block;
  width: 25%;
  height: 50px;
  text-align: center;
}
.list-header > p:first-child {
  color: #ff5604;
  font-size: 12px;
  font-weight: bold;
}
.list-header > p:last-child {
  color: #fff;
  font-size: 12px;
}
.header-text {
  font-size: 6px;
}
.line {
  width: 20px;
  height: 1px;
  background: #fff;
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
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
#echarts-container {
  width: 100%;
  height: 360px;
}
</style>
