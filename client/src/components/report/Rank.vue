<template>
  <div id="main3">
<<<<<<< HEAD

=======
    <div id="main3_1" style="float:left"></div>
    <div id="main3_2" style="float:left"></div>
    <div id="main3_3" style="float:left"></div>
>>>>>>> bb3d1b7 (增加了大屏)
  </div>
</template>

<script>
import * as echarts from 'echarts';
let myChart;
<<<<<<< HEAD
=======
let myChart2;
let myChart3;
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
      var chartDom = document.getElementById('main3');
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
  
      var chartDom = document.getElementById('main3_1');
      var chartDom2 = document.getElementById('main3_2');
      var chartDom3 = document.getElementById('main3_3');
      myChart = echarts.init(chartDom);
      myChart2 = echarts.init(chartDom2);
      myChart3 = echarts.init(chartDom3);
      var option;
      var option2;
      var option3;
      const gaugeData = [
        {
          value: 20,
          name: 'Good',
          title: {
            offsetCenter: ['-40%', '80%']
          },
          detail: {
            offsetCenter: ['-40%', '95%']
          }
        },
        {
          value: 40,
          name: 'Better',
          title: {
            offsetCenter: ['0%', '80%']
          },
          detail: {
            offsetCenter: ['0%', '95%']
          }
        },
        {
          value: 60,
          name: 'Perfect',
          title: {
            offsetCenter: ['40%', '80%']
          },
          detail: {
            offsetCenter: ['40%', '95%']
          }
        }
      ];
      option = {
        tooltip: {
          formatter: '{a} <br/>{b} : {c}%'
        },
        series: [
          {
            name: 'Pressure',
            type: 'gauge',
            detail: {
              formatter: '{value}'
            },
            data: [
              {
                value: 50,
                name: 'SCORE'
              }
            ]
          }
        ]
      };
      option2 = {
        tooltip: {
          formatter: '{a} <br/>{b} : {c}%'
        },
        series: [
          {
            name: 'Pressure',
            type: 'gauge',
            detail: {
              formatter: '{value}'
            },
            data: [
              {
                value: 50,
                name: 'SCORE'
              }
            ]
          }
        ]
      };
      option3 = {
        tooltip: {
          formatter: '{a} <br/>{b} : {c}%'
        },
        series: [
          {
            name: 'Pressure',
            type: 'gauge',
            detail: {
              formatter: '{value}'
            },
            data: [
              {
                value: 50,
                name: 'SCORE'
              }
            ]
          }
        ]
      };
      option && myChart.setOption(option);
      option2 && myChart2.setOption(option2);
      option3 && myChart3.setOption(option3);
>>>>>>> bb3d1b7 (增加了大屏)

    }

  }
}



</script>

<style lang="less" scoped>
<<<<<<< HEAD
#main3{
  width: 440px;
  height: 400px;
}</style>
=======
#main3 {
 width: 600px;
  height: 400px;
  border-style: solid;
  border-width: 5px;
  border-color: #98bf21;

}
#main3_1{
  width: 200px;
  height: 300px;
  float: left;
 
}
#main3_2{
  width: 200px;
  height: 300px;
  float: left;

}
#main3_3{
  width: 200px;
  height: 300px;
  float: left;

}
</style>
>>>>>>> bb3d1b7 (增加了大屏)
