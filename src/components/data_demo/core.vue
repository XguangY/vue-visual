<template>
  <dv-border-box-11 class="chart-container" title="今日仓位">
    <div class="chart-container-center">
      <div class="chart-container-center-top">
        <dv-border-box-13 class="chart-container-center-top-left">美元指数</dv-border-box-13>
        <dv-decoration-1 class="chart-container-center-top-left" />
      </div>
      <div ref="chart" style="width:100%;height:230px" />
      <dv-decoration-10 class="chart-container-center-line" />
      <div class="chart-container-center-fa">
        <div>
          <div class="chart-container-center-fa-con">
            <dv-decoration-11 style="width:200px;height:60px;">今日关注板块</dv-decoration-11>
          </div>
          <div class="chart-container-center-fa-block">
            <dv-border-box-12 class="chart-container-center-fa-block-item">基建板块</dv-border-box-12>
            <dv-border-box-12 class="chart-container-center-fa-block-item">军工板块</dv-border-box-12>
            <dv-border-box-12 class="chart-container-center-fa-block-item">石油化工板块</dv-border-box-12>
            <dv-border-box-12 class="chart-container-center-fa-block-item">概念板块</dv-border-box-12>
            <dv-border-box-12 class="chart-container-center-fa-block-item">能源板块</dv-border-box-12>
            <dv-border-box-12 class="chart-container-center-fa-block-item">航空板块</dv-border-box-12>
            <dv-border-box-12 class="chart-container-center-fa-block-item">更多板块...</dv-border-box-12>
          </div>
        </div>
        <dv-decoration-4 style="width:5px;height:370px;padding-top:6px" />
        <div>
          <div class="chart-container-center-fa-con">
            <dv-decoration-11 style="width:200px;height:60px;">今日股票池</dv-decoration-11>
          </div>
          <div ref="pond" class="chart-container-center-fa-pond" />
        </div>
      </div>
    </div>
  </dv-border-box-11>
</template>
<script>
export default {
  name: 'Core',
  data() {
    return {}
  },
  mounted() {
    this.getEchartData()
    this.aa()
  },
  methods: {
    getEchartData() {
      const chart = this.$refs.chart
      let myChart, timer
      const option = {
        tooltip: {
          trigger: 'item',
          formatter: '{a} <br/>{b} : {c} ({d}%)'
        },

        visualMap: {
          show: false,
          min: 80,
          max: 600,
          inRange: {
            colorLightness: [0, 1]
          }
        },
        series: [
          {
            name: '仓位占比',
            type: 'pie',
            radius: '90%',
            center: ['50%', '50%'],
            data: [
              { value: 335, name: '概念板块' },
              { value: 310, name: '军工板块' },
              { value: 274, name: '基建板块' },
              { value: 235, name: '石油化工板块' },
              { value: 400, name: '能源板块' }
            ].sort(function(a, b) {
              return a.value - b.value
            }),
            roseType: 'radius',
            label: {
              color: 'rgba(255, 255, 255, 1.0)'
            },
            labelLine: {
              lineStyle: {
                color: 'rgba(255, 255, 255, 1.0)'
              },
              smooth: 0.2,
              length: 10,
              length2: 20
            },
            itemStyle: {
              normal: {
                shadowBlur: 200,
                shadowColor: 'rgba(0, 0, 0, 0.5)'
              }
            },

            animationType: 'scale',
            animationEasing: 'elasticOut',
            animationDelay: function(idx) {
              return Math.random() * 200
            }
          }
        ]
      }
      if (chart) {
        myChart = this.$echarts.init(chart)
        myChart.setOption(option)
        window.addEventListener('resize', function() {
          myChart.resize()
        })
      }
      this.$on('hook:destroyed', () => {
        window.removeEventListener('resize', function() {
          myChart.resize()
        })
      })
      // 处理点击事件并且跳转到相应的百度搜索页面
      myChart.on('mouseover', function(params) {
        if (timer) {
          // 取消之前高亮的图形
          myChart.dispatchAction({
            type: 'downplay',
            seriesIndex: 0,
            dataIndex: chart.currentIndex
          })
          clearInterval(timer)
          timer = null
        }
      })
      myChart.on('mouseout', function(params) {
        if (!timer) {
          timer = setInterval(timerFN, 2000)
        }
      })
      chart.currentIndex = -1

      timer = setInterval(timerFN, 2000)

      function timerFN() {
        var dataLen = option.series[0].data.length
        // 取消之前高亮的图形
        myChart.dispatchAction({
          type: 'downplay',
          seriesIndex: 0,
          dataIndex: chart.currentIndex
        })
        chart.currentIndex = (chart.currentIndex + 1) % dataLen
        // 高亮当前图形
        myChart.dispatchAction({
          type: 'highlight',
          seriesIndex: 0,
          dataIndex: chart.currentIndex
        })
        // 显示 tooltip
        myChart.dispatchAction({
          type: 'showTip',
          seriesIndex: 0,
          dataIndex: chart.currentIndex
        })
      }
    },
    aa() {
      var chartPond = this.$echarts.init(this.$refs.pond)

      var option = {
        tooltip: {},
        // backgroundColor: 'rgba(6, 30, 93, 0.1)',
        series: [
          {
            type: 'wordCloud',
            gridSize: 2,
            sizeRange: [12, 50],
            rotationRange: [-90, 90],
            shape: 'pentagon',
            width: '100%',
            height: '100%',
            drawOutOfBound: true,
            textStyle: {
              normal: {
                color: function() {
                  return (
                    'rgb(' +
                    [
                      Math.round(Math.random() * 160),
                      Math.round(Math.random() * 160),
                      Math.round(Math.random() * 160)
                    ].join(',') +
                    ')'
                  )
                }
              },
              emphasis: {
                shadowBlur: 10,
                shadowColor: 'blue'
              }
            },
            data: [
              {
                name: '航天晨光',
                value: 10000,
                textStyle: {
                  normal: {
                    color: 'pink'
                  },
                  emphasis: {
                    color: 'red'
                  }
                }
              },
              {
                name: '贵州茅台',
                value: 6181
              },
              {
                name: '华北制药',
                value: 4386
              },
              {
                name: '山西汾酒',
                value: 4055
              },
              {
                name: '中国铁建',
                value: 2467
              },
              {
                name: '航发科技',
                value: 2244
              },
              {
                name: '中环环保',
                value: 1898
              },
              {
                name: '航天晨光',
                value: 1484
              },
              {
                name: '中国铁建',
                value: 1112
              },
              {
                name: '华北制药',
                value: 965
              },
              {
                name: '贵州茅台',
                value: 847
              },
              {
                name: '洪都航空',
                value: 582
              },
              {
                name: '山西汾酒',
                value: 555
              },
              {
                name: '贵州茅台',
                value: 550
              },
              {
                name: '洪都航空',
                value: 462
              },
              {
                name: '酷特智能',
                value: 366
              },
              {
                name: '山西汾酒',
                value: 360
              },
              {
                name: '中环环保',
                value: 282
              },
              {
                name: '航发科技',
                value: 273
              },
              {
                name: '酷特智能',
                value: 265
              }
            ]
          }
        ]
      }
      // 添加点击事件,获取自定义属性
      chartPond.on('click', function(params) {
        var name = params.data.name
        var value = params.data.value
        var uniscid = params.data.uniscid
        console.log(name + ':' + value + ':' + uniscid)
      })
      chartPond.setOption(option)
    }
  }
}
</script>
<style lang="scss" scope>
.chart-container {
  padding: 70px 30px 30px;
  display: flex;
  box-sizing: border-box;
  &-center {
    &-top {
      display: flex;
      justify-content: space-between;
      line-height: 60px;
      text-align: center;
      &-left {
        width: 120px;
        height: 56px;
      }
    }
    &-fa {
      display: flex;
      > div {
        width: 50%;
      }
      &-con {
        display: flex;
        justify-content: center;
        margin-bottom: 10px;
      }
      &-block {
        display: flex;
        flex-wrap: wrap;
        &-item {
          width: 50%;
          text-align: center;
          margin: 8px 0;
          line-height: 60px;
          height: 60px;
        }
        &-item:last-child {
          width: 100%;
        }
      }
      &-pond {
        height: 300px;
      }
    }
    &-line {
      margin: 10px 0;
      height: 5px;
    }
  }
}
</style>
