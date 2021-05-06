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
        data: ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子']
      },
      yAxis: {},
      series: [{
        name: '销量',
        type: 'bar',
        data: [5, 20, 36, 10, 10, 70]
      }]
    })
  }
}
</script>

<style>
#app{
  margin: 100px auto;
  width: 400px;
  height: 200px;
}
</style>
