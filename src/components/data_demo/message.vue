<template>
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
</template>
<script>
export default {
  name: 'Message',
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
      }
    }
  }
}
</script>
<style lang="scss" scope>
.chart-container {
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
}
</style>
