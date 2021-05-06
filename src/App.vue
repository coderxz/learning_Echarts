<template>
  <div id="app" ref="app">
    app
  </div>
</template>

<script>


export default {
  name: 'App',
  mounted(){
    let {$Echarts} = this
    $Echarts.init(this.$refs.app).setOption({
      title: {
        text: 'ECharts 入门示例'
      },
      tooltip: {},
      xAxis: {
        data: ['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec']
      },
      yAxis: {},
      //系列指的是一组数值以及他们映射成的图，包含的要素至少有：一组数值、图表类型（series.type）、以及其他的关于这些数据如何映射成图的参数。
      series: [
        {
          type:'pie',
          center:['65%',60],
          radius:35,
          data:[
            {name:'xxx',value:52},
            {name:'yyy',value:23},
            {name:'ddd',value:24},
          ]
        },
        {
          type:'line',
          data:[34,28,45,69,39,43,33,23,23,33,39,22]
        },
        {
          type:'bar',
          data:[20,14,32,46,24,34,23,12,14,23,26,17]
        },
      ]
    })
  }
}
</script>

<style>
#app{
  margin: 100px auto;
  width: 600px;
  height: 600px;
}
</style>
