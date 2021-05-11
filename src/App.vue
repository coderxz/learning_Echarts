<template>
  <div id="app" ref="app">
    app
  </div>
</template>

<script>


export default {
  name: 'App',
  mounted() {
    let {$Echarts} = this
    console.log(this.$refs.app)
    //基础图形
    // let baseMap = {
    //   title: {
    //     text: 'ECharts'
    //   },
    //   tooltip: {},
    //   //直角坐标系 X 轴
    //   xAxis: {
    //     data: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec']
    //   },
    //   //直角坐标系 Y 轴
    //   yAxis: {},
    //   //系列指的是一组数值以及他们映射成的图，包含的要素至少有：一组数值、图表类型（series.type）、以及其他的关于这些数据如何映射成图的参数。
    //   series: [
    //     {
    //       type: 'pie',
    //       //控制饼图的位置，第一个参数是x轴方向，第二个参数是Y轴方向，少数圆形的组件或系列，可以使用“中心半径定位”，例如，pie（饼图）、sunburst（旭日图）、polar（极坐标系）。
    //       center: ['75%', 80],
    //       //控制饼图的大小，值是旋转半径
    //       radius: 70,
    //       data: [
    //         {name: 'xxx', value: 52},
    //         {name: 'yyy', value: 23},
    //         {name: 'ddd', value: 24},
    //       ]
    //     },
    //     {
    //       type: 'line',
    //       data: [34, 28, 45, 69, 39, 43, 33, 23, 23, 33, 39, 22]
    //     },
    //     {
    //       type: 'bar',
    //       data: [20, 14, 32, 46, 24, 34, 23, 12, 14, 23, 26, 17]
    //     },
    //   ],
    //   //直角坐标系底板,设置坐标轴上下左右的位置
    //   grid: {
    //     left: 200,
    //     right: '30%',
    //     height: '40%',
    //     bottom: 110
    //   }
    // }

    //南丁格尔图
    // let NanDingGeReMap = {
    //   backgroundColor: '#2c343c',
    //   visualMap: {
    //     show: false,
    //     min: 80,
    //     max: 600,
    //     inRange: {
    //       colorLightness: [0, 1]
    //     }
    //   },
    //   series: [
    //     {
    //       name: '访问来源',
    //       type: 'pie',
    //       radius: '55%',
    //       data: [
    //         {value: 235, name: '视频广告'},
    //         {value: 274, name: '联盟广告'},
    //         {value: 310, name: '邮件营销'},
    //         {value: 335, name: '直接访问'},
    //         {value: 400, name: '搜索引擎'}
    //       ],
    //       roseType: 'angle',
    //       label: {
    //         normal: {
    //           textStyle: {
    //             color: 'rgba(255, 255, 255, 0.3)'
    //           }
    //         }
    //       },
    //       labelLine: {
    //         normal: {
    //           lineStyle: {
    //             color: 'rgba(255, 255, 255, 0.3)'
    //           }
    //         }
    //       },
    //       itemStyle: {
    //         normal: {
    //           color: '#c23531',
    //           shadowBlur: 200,
    //           shadowColor: 'rgba(0, 0, 0, 0.5)'
    //         }
    //       }
    //     }
    //   ]
    // };

    //饼状图
    var ROOT_PATH = 'https://cdn.jsdelivr.net/gh/apache/echarts-website@asf-site/examples';
    let option = {
    backgroundColor: '#000',
    globe: {
        baseTexture: ROOT_PATH + "/data-gl/asset/world.topo.bathy.200401.jpg",
        heightTexture: ROOT_PATH + "/data-gl/asset/world.topo.bathy.200401.jpg",
        displacementScale: 0.04,
        shading: 'realistic',
        environment: ROOT_PATH + '/data-gl/asset/starfield.jpg',
        realisticMaterial: {
            roughness: 0.9
        },
        postEffect: {
            enable: true
        },
        light: {
            main: {
                intensity: 5,
                shadow: true
            },
            ambientCubemap: {
                texture: ROOT_PATH + '/data-gl/asset/pisa.hdr',
                diffuseIntensity: 0.2
            }
        }
    }
};
    $Echarts.init(this.$refs.app).setOption(option)
  }
}
</script>

<style>
#app {
  margin: 100px auto;
  width:  800px;
  height: 800px;
}
</style>
