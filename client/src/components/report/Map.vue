<template>
  <div id="main2">

  </div>
</template>

<script>
import * as echarts from 'echarts';
let myChart;
export default {
  mounted() {
    this.init()

  },

  methods: {
    init() {
      if (myChart != null && myChart != "" && myChart != undefined) {
        myChart.dispose();//销毁
    }
      var chartDom = document.getElementById('main2');
      myChart = echarts.init(chartDom);
      var option;

      option = {
        xAxis: {
          type: 'category',
          data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
        },
        yAxis: {
          type: 'value'
        },
        series: [
          {
            data: [120, 200, 150, 80, 70, 110, 130],
            type: 'bar',
            showBackground: true,
            backgroundStyle: {
              color: 'rgba(180, 180, 180, 0.2)'
            }
          }
        ]
      };

      option && myChart.setOption(option);

    }

  }
}



</script>

<style lang="less" scoped>
#main2{
  width: 440px;
  height: 400px;
}</style>