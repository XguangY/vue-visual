<template>
  <div class="main-content">
    <div class="left-chart">
      <dv-border-box-11 class="left-chart-container" title="今日资讯">
        <dv-decoration-7 class="left-chart-container-title">国际资讯</dv-decoration-7>
        <dv-scroll-board class="left-chart-container-table" :config="config" />

        <dv-decoration-7 class="left-chart-container-title">国家资讯</dv-decoration-7>
        <dv-scroll-board class="left-chart-container-table" :config="config" />

        <dv-decoration-7 style="width: 140px" class="left-chart-container-title">关注板块资讯</dv-decoration-7>
        <dv-scroll-board class="left-chart-container-table" :config="config" />

        <dv-decoration-7 class="left-chart-container-title">个人资讯</dv-decoration-7>
        <dv-scroll-board class="left-chart-container-table" :config="config" />
      </dv-border-box-11>
      <dv-border-box-11 class="left-chart-container" title="今日仓位">2</dv-border-box-11>
      <dv-border-box-11 class="left-chart-container" title="今日操盘策略">
        <dv-decoration-11 style="width:150px;height:60px;">策略一</dv-decoration-11>
        <dv-decoration-9 style="width:150px;height:150px;">策略二</dv-decoration-9>
      </dv-border-box-11>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TopHeader',
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
.main-content {
  flex: 1;
  display: flex;
  flex-direction: column;
  .left-chart {
    display: flex;
    height: 100%;
    &-container {
      padding: 70px 30px 30px;
      display: flex;
      box-sizing: border-box;
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
}
</style>
