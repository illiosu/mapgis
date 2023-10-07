<template>
  <div id="main4">

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
<<<<<<< HEAD
    }
=======
      }
>>>>>>> bb3d1b7 (增加了大屏)
      var chartDom = document.getElementById('main4');
      myChart = echarts.init(chartDom);
      var option;

<<<<<<< HEAD
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

=======
      function randomData() {
  now = new Date(+now + oneDay);
  value = value + Math.random() * 21 - 10;
  return {
    name: now.toString(),
    value: [
      [now.getFullYear(), now.getMonth() + 1, now.getDate()].join('/'),
      Math.round(value)
    ]
  };
}
let data = [];
let now = new Date(1997, 9, 3);
let oneDay = 24 * 3600 * 1000;
let value = Math.random() * 1000;
for (var i = 0; i < 1000; i++) {
  data.push(randomData());
}
option = {
  title: {
    text: '历年污染排放量'
  },
  tooltip: {
    trigger: 'axis',
    formatter: function (params) {
      params = params[0];
      var date = new Date(params.name);
      return (
        date.getDate() +
        '/' +
        (date.getMonth() + 1) +
        '/' +
        date.getFullYear() +
        ' : ' +
        params.value[1]
      );
    },
    axisPointer: {
      animation: false
    }
  },
  xAxis: {
    type: 'time',
    splitLine: {
      show: false
    }
  },
  yAxis: {
    type: 'value',
    boundaryGap: [0, '100%'],
    splitLine: {
      show: false
    }
  },
  series: [
    {
      name: 'Fake Data',
      type: 'line',
      showSymbol: false,
      data: data
    }
  ]
};
setInterval(function () {
  for (var i = 0; i < 5; i++) {
    data.shift();
    data.push(randomData());
  }
  myChart.setOption({
    series: [
      {
        data: data
      }
    ]
  });
}, 1000);
>>>>>>> bb3d1b7 (增加了大屏)
      option && myChart.setOption(option);

    }

  }
}



</script>

<style lang="less" scoped>
<<<<<<< HEAD
#main4{
  width: 440px;
  height: 400px;
}</style>
=======
#main4 {
  width: 300px;
  height: 300px;
  border-style: solid;
  border-width: 5px;
  border-color: #98bf21;
}
</style>
>>>>>>> bb3d1b7 (增加了大屏)
