<template>
<<<<<<< HEAD
  <div id="main6">

=======
  <div id="container">
    <div id="main6">
    </div>
 
 
>>>>>>> bb3d1b7 (增加了大屏)
  </div>
</template>

<script>
import * as echarts from 'echarts';
let myChart;
<<<<<<< HEAD
=======
let myChart2;
>>>>>>> bb3d1b7 (增加了大屏)
export default {
  mounted() {
    this.init()

  },

  methods: {
    init() {
<<<<<<< HEAD
      if (myChart != null && myChart != "" && myChart != undefined) {
        myChart.dispose();//销毁
    }
      var chartDom = document.getElementById('main6');
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

=======
  
      var chartDom = document.getElementById('main6');

      myChart = echarts.init(chartDom);
  
      var option;
      var option2;

      setTimeout(function () {
  option = {
    legend: {},
    tooltip: {
      trigger: 'axis',
      showContent: false
    },
    dataset: {
      source: [
        ['product', '2012', '2013', '2014', '2015', '2016', '2017'],
        ['Milk Tea', 56.5, 82.1, 88.7, 70.1, 53.4, 85.1],
        ['Matcha Latte', 51.1, 51.4, 55.1, 53.3, 73.8, 68.7],
        ['Cheese Cocoa', 40.1, 62.2, 69.5, 36.4, 45.2, 32.5],
        ['Walnut Brownie', 25.2, 37.1, 41.2, 18, 33.9, 49.1]
      ]
    },
    xAxis: { type: 'category' },
    yAxis: { gridIndex: 0 },
    grid: { top: '55%' },
    series: [
      {
        type: 'line',
        smooth: true,
        seriesLayoutBy: 'row',
        emphasis: { focus: 'series' }
      },
      {
        type: 'line',
        smooth: true,
        seriesLayoutBy: 'row',
        emphasis: { focus: 'series' }
      },
      {
        type: 'line',
        smooth: true,
        seriesLayoutBy: 'row',
        emphasis: { focus: 'series' }
      },
      {
        type: 'line',
        smooth: true,
        seriesLayoutBy: 'row',
        emphasis: { focus: 'series' }
      },
      {
        type: 'pie',
        id: 'pie',
        radius: '30%',
        center: ['50%', '25%'],
        emphasis: {
          focus: 'self'
        },
        label: {
          formatter: '{b}: {@2012} ({d}%)'
        },
        encode: {
          itemName: 'product',
          value: '2012',
          tooltip: '2012'
        }
      }
    ]
  };
  myChart.on('updateAxisPointer', function (event) {
    const xAxisInfo = event.axesInfo[0];
    if (xAxisInfo) {
      const dimension = xAxisInfo.value + 1;
      myChart.setOption({
        series: {
          id: 'pie',
          label: {
            formatter: '{b}: {@[' + dimension + ']} ({d}%)'
          },
          encode: {
            value: dimension,
            tooltip: dimension
          }
        }
      });
    }
  });
  myChart.setOption(option);
});
>>>>>>> bb3d1b7 (增加了大屏)
    }

  }
}



</script>

<style lang="less" scoped>
<<<<<<< HEAD
#main6{
  width: 440px;
  height: 400px;
}</style>
=======
#main6 {
  width: 300px;
  height: 300px;

}
#main6_1{
  width: 300px;
  height: 100px;
}
#container {
  border-style: solid;
  border-width: 5px;
  border-color: #98bf21;
  width: 300px;
  height: 400px;

}
#test{
bottom: 50px;
  position: absolute;
  background-color: black;
}
</style>
>>>>>>> bb3d1b7 (增加了大屏)
