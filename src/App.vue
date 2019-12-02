<template>
  <div id="app">
    <div id="main" style="width: 600px;height:400px;"></div>
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>

  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import * as echarts from 'echarts'
//var echarts = require('echarts');
export default {
  name: 'app',
  components: {
    HelloWorld
  },
  mounted() {
    let myChart = echarts.init(document.getElementById('main'));
      let option =  {
          xAxis: {
              type: 'category',
              boundaryGap: false,
              data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
          },
          yAxis: {
              type: 'value'
          },
          series: [{
              data: [820, 932, 901, 934, 1290, 1330, 1320],
              type: 'line',
              areaStyle: {}
          }]
      };
    
      // 使用刚指定的配置项和数据显示图表。
      myChart.setOption(option);
  },
  methods:{
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
