<template>
  <div class="main-content">
    <div class="chart">
      <dv-border-box-11 class="chart-container" title="今日资讯">
        <dv-decoration-7 class="chart-container-left-title">国际资讯</dv-decoration-7>
        <dv-scroll-board class="chart-container-left-table" :config="config" />

        <dv-decoration-7 class="chart-container-left-title">国家资讯</dv-decoration-7>
        <dv-scroll-board class="chart-container-left-table" :config="config" />

        <dv-decoration-7 style="width: 140px" class="chart-container-left-title">关注板块资讯</dv-decoration-7>
        <dv-scroll-board class="chart-container-left-table" :config="config" />

        <dv-decoration-7 class="chart-container-left-title">个人资讯</dv-decoration-7>
        <dv-scroll-board class="chart-container-left-table" :config="config" />
      </dv-border-box-11>
      <dv-border-box-11 class="chart-container" title="今日仓位">
        <div class="chart-container-center">
          <div class="chart-container-center-top">
            <dv-border-box-13 class="chart-container-center-top-left">美元指数</dv-border-box-13>
            <dv-decoration-1 class="chart-container-center-top-left" />
          </div>
          <div ref="chart" style="width:100%;height:230px" />
          <dv-decoration-10 class="chart-container-center-line" />
          <div class="chart-container-center-con">
            <dv-decoration-11 style="width:200px;height:60px;">今日关注板块</dv-decoration-11>
          </div>
          <div class="chart-container-center-block">
            <dv-border-box-12 class="chart-container-center-block-item">基建板块</dv-border-box-12>
            <dv-border-box-12 class="chart-container-center-block-item">军工板块</dv-border-box-12>
            <dv-border-box-12 class="chart-container-center-block-item">石油化工板块</dv-border-box-12>
            <dv-border-box-12 class="chart-container-center-block-item">概念板块</dv-border-box-12>
          </div>
          <dv-decoration-10 class="chart-container-center-line" />
          <div class="chart-container-center-con">
            <dv-decoration-11 style="width:200px;height:60px;">今日股票池</dv-decoration-11>
          </div>
          <div ref="pond" class="chart-container-center-pond" />
        </div>
      </dv-border-box-11>
      <dv-border-box-11 class="chart-container" title="今日操盘策略">
        <div v-for="(item, index) in strategy_data" :key="index">
          <div class="chart-container-right">
            <dv-decoration-9 class="chart-container-right-strategy">{{ item.title }}</dv-decoration-9>
            <div class="chart-container-right-con">
              <div class="chart-container-right-con-item">
                <div>当前持仓</div>
                <div>
                  <div v-for="(ite, ind) in item.data_now" :key="ind">
                    <span v-text="`${ite.type_name}:`" />
                    <span v-for="(ele, num) in ite.data" :key="num" v-text="`${ele.name}、`" />
                  </div>
                </div>
              </div>
              <div class="chart-container-right-con-item">
                <div>今日新增</div>
                <div>
                  <div v-for="(ite, ind) in item.data_add" :key="ind">
                    <span v-text="`${ite.type_name}:`" />
                    <span v-for="(ele, num) in ite.data" :key="num" v-text="`${ele.name}、`" />
                  </div>
                </div>
              </div>
            </div>
          </div>
          <dv-decoration-2 class="chart-container-line" />
        </div>

        <div class="chart-container-right">
          <dv-border-box-8 class="chart-container-right-img">
            <img src="https://www.ditingai.com/skin/assets/common/images/dt-logo.png">
          </dv-border-box-8>
          <div style="text-align: center;">
            让投资变得更简单
            <dv-decoration-3 style="width:220px;height:30px;" />
          </div>

          <a href="https://www.ditingai.com/" target="_blank">
            <dv-decoration-11 style="width:200px;height:60px;">自营平台</dv-decoration-11>
          </a>
        </div>
      </dv-border-box-11>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Content',
  data() {
    return {
      config: {
        data: [
          [
            '<span style="color:#37a2da;">公募化改造资管产品二季报出炉 重仓股名单曝光</span>'
          ],
          [
            '<span style="color:#32c5e9;">蚂蚁集团上市：这次突破了A股股民对财富的想象力</span>'
          ],
          [
            '<span style="color:#67e0e3;">粤开策略：创业板指依旧是此轮反弹行情的先行指标</span>'
          ],
          [
            '<span style="color:#9fe6b8;">超级大单：万亿白马股被砸盘 大资金抛售11亿</span>'
          ],
          [
            '<span style="color:#ffdb5c;">公募化改造资管产品二季报出炉 重仓股名单曝光</span>'
          ],
          [
            '<span style="color:#ff9f7f;">蚂蚁集团上市：这次突破了A股股民对财富的想象力</span>'
          ],
          [
            '<span style="color:#fb7293;">粤开策略：创业板指依旧是此轮反弹行情的先行指标</span>'
          ],
          [
            '<span style="color:#e062ae;">超级大单：万亿白马股被砸盘 大资金抛售11亿</span>'
          ],
          [
            '<span style="color:#e690d1;">蚂蚁集团上市：这次突破了A股股民对财富的想象力</span>'
          ],
          [
            '<span style="color:#e7bcf3;">公募化改造资管产品二季报出炉 重仓股名单曝光</span>'
          ]
        ],
        waitTime: 5000,
        rowNum: 3,
        headerBGC: '#1981f6',
        headerHeight: 45,
        oddRowBGC: 'rgba(0, 44, 81, 0.8)',
        evenRowBGC: 'rgba(10, 29, 50, 0.8)'
      },
      strategy_data: [
        {
          type: 0,
          title: '策略一',
          data_now: [
            {
              type_name: '概念板块',
              data: [
                { name: '贵州茅台[600519]' },
                { name: '山西汾酒[600809]' },
                { name: '五粮液[000858]' }
              ]
            },
            {
              type_name: '军工板块',
              data: [
                { name: '航天晨光[600501]' },
                { name: '东安动力[600178]' },
                { name: '航发科技[600391]' }
              ]
            }
          ],
          data_add: [
            {
              type_name: '基建板块',
              data: [
                { name: '中国交建[601800]' },
                { name: '中国建筑[601668]' },
                { name: '中国铁建[601186]' }
              ]
            }
          ]
        },
        {
          type: 1,
          title: '策略二',
          data_now: [
            {
              type_name: '概念板块',
              data: [
                { name: '贵州茅台[600519]' },
                { name: '山西汾酒[600809]' },
                { name: '五粮液[000858]' }
              ]
            },
            {
              type_name: '军工板块',
              data: [
                { name: '航天晨光[600501]' },
                { name: '东安动力[600178]' },
                { name: '航发科技[600391]' }
              ]
            },
            {
              type_name: '军工板块',
              data: [
                { name: '航天晨光[600501]' },
                { name: '东安动力[600178]' },
                { name: '航发科技[600391]' }
              ]
            }
          ],
          data_add: [
            {
              type_name: '基建板块',
              data: [
                { name: '中国交建[601800]' },
                { name: '中国建筑[601668]' },
                { name: '中国铁建[601186]' }
              ]
            }
          ]
        },
        {
          type: 2,
          title: '策略三',
          data_now: [
            {
              type_name: '概念板块',
              data: [
                { name: '贵州茅台[600519]' },
                { name: '山西汾酒[600809]' },
                { name: '五粮液[000858]' }
              ]
            },
            {
              type_name: '军工板块',
              data: [
                { name: '航天晨光[600501]' },
                { name: '东安动力[600178]' },
                { name: '航发科技[600391]' }
              ]
            }
          ],
          data_add: [
            {
              type_name: '基建板块',
              data: [
                { name: '中国交建[601800]' },
                { name: '中国建筑[601668]' },
                { name: '中国铁建[601186]' }
              ]
            }
          ]
        }
      ]
    }
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
                    color: 'black'
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
.main-content {
  flex: 1;
  display: flex;
  flex-direction: column;
  .chart {
    display: flex;
    height: 100%;
    &-container {
      padding: 70px 30px 30px;
      display: flex;
      box-sizing: border-box;
      &-left {
        &-title {
          margin: 10px 0;
          width: 110px;
          height: 20px;
        }
        &-title:first-child {
          margin-top: 0;
        }
        &-table {
          height: 132px;
        }
      }
      &-center {
        &-top {
          display: flex;
          justify-content: space-between;
          line-height: 56px;
          text-align: center;
          &-left {
            width: 120px;
            height: 56px;
          }
        }
        &-con {
          display: flex;
          justify-content: center;
          margin-bottom: 10px;
        }
        &-block {
          display: flex;
          &-item {
            // width: 100px;
            text-align: center;
            margin: 0 10px;
            line-height: 60px;
            height: 60px;
          }
        }
        &-line {
          margin: 10px 0;
          height: 5px;
        }
        &-pond {
          // width: 100%;
          height: 150px;
        }
      }
      &-right {
        display: flex;
        align-items: center;
        &-strategy {
          height: 80px;
          width: 80px;
        }
        &-con {
          display: flex;
          flex-direction: column;
          padding-left: 10px;
          width: 86%;
          &-item {
            flex-grow: 1;
            display: flex;
            // align-items: center;
            margin-bottom: 10px;
            > div:first-child {
              font-size: 22px;
              color: #ea6027;
              width: 60px;
              text-align: center;
            }
            div {
              color: #67e0e3;
            }
          }
        }
        &-img {
          width: 160px;
          height: 160px;
          position: relative;
          img {
            position: absolute;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            width: 140px;
            height: 140px;
          }
        }
      }
      &-line {
        height: 20px;
      }
    }
  }
}
</style>
