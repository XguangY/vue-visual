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
      <dv-border-box-11 class="chart-container" title="今日仓位">2</dv-border-box-11>
      <dv-border-box-11 class="chart-container" title="今日操盘策略">
        <div class="chart-container-right">
          <dv-decoration-9 class="chart-container-right-strategy">策略一</dv-decoration-9>
          <div class="chart-container-right-con">
            <div class="chart-container-right-con-item">
              <div>当前持仓</div>
              <div>
                <div>概念板块：贵州茅台[600519]、山西汾酒[600809]、 五粮液[000858]</div>
                <div>军工板块：航天晨光[600501]、东安动力[600178]、航发科技[600391]...</div>
                <div>军工板块：航天晨光[600501]、东安动力[600178]、航发科技[600391]...</div>
              </div>
            </div>
            <div class="chart-container-right-con-item">
              <div>今日新增</div>
              <div>
                <div>基建板块：中国交建[601800]、中国建筑[601668]、中国铁建[601186]</div>
              </div>
            </div>
          </div>
        </div>
        <dv-decoration-2 class="chart-container-line" />
        <div class="chart-container-right">
          <dv-decoration-9 class="chart-container-right-strategy">策略二</dv-decoration-9>
          <div class="chart-container-right-con">
            <div class="chart-container-right-con-item">
              <div>当前持仓</div>
              <div>
                <div>概念板块：贵州茅台[600519]、山西汾酒[600809]、 五粮液[000858]</div>
                <div>军工板块：航天晨光[600501]、东安动力[600178]、航发科技[600391]...</div>
              </div>
            </div>
            <div class="chart-container-right-con-item">
              <div>今日新增</div>
              <div>
                <div>基建板块：中国交建[601800]、中国建筑[601668]、中国铁建[601186]</div>
              </div>
            </div>
          </div>
        </div>
        <dv-decoration-2 class="chart-container-line" />
        <div class="chart-container-right">
          <dv-decoration-9 class="chart-container-right-strategy">策略三</dv-decoration-9>
          <div class="chart-container-right-con">
            <div class="chart-container-right-con-item">
              <div>当前持仓</div>
              <div>
                <div>概念板块：贵州茅台[600519]、山西汾酒[600809]、 五粮液[000858]</div>
                <div>军工板块：航天晨光[600501]、东安动力[600178]、航发科技[600391]...</div>
              </div>
            </div>
            <div class="chart-container-right-con-item">
              <div>今日新增</div>
              <div>
                <div>基建板块：中国交建[601800]、中国建筑[601668]、中国铁建[601186]</div>
              </div>
            </div>
          </div>
        </div>
        <dv-decoration-2 class="chart-container-line" />

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
      }
    }
  },
  methods: {}
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
