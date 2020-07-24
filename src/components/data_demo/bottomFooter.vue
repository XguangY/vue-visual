<template>
  <div id="bottom-footer">
    <dv-border-box-10>
      <div class="footer">
        <div class="footer-item footer-left">
          <el-avatar
            :size="80"
            src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1595594850091&di=449a96212ce98fa028c29494e64535c5&imgtype=0&src=http%3A%2F%2Fimg3.imgtn.bdimg.com%2Fit%2Fu%3D1590662363%2C713073460%26fm%3D214%26gp%3D0.jpg"
          />
          <el-avatar
            :size="80"
            src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1595594850091&di=449a96212ce98fa028c29494e64535c5&imgtype=0&src=http%3A%2F%2Fimg3.imgtn.bdimg.com%2Fit%2Fu%3D1590662363%2C713073460%26fm%3D214%26gp%3D0.jpg"
          />
          <el-avatar
            :size="80"
            src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1595594850091&di=449a96212ce98fa028c29494e64535c5&imgtype=0&src=http%3A%2F%2Fimg3.imgtn.bdimg.com%2Fit%2Fu%3D1590662363%2C713073460%26fm%3D214%26gp%3D0.jpg"
          />
          <el-avatar
            :size="80"
            src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1595594850091&di=449a96212ce98fa028c29494e64535c5&imgtype=0&src=http%3A%2F%2Fimg3.imgtn.bdimg.com%2Fit%2Fu%3D1590662363%2C713073460%26fm%3D214%26gp%3D0.jpg"
          />
          <el-avatar
            :size="80"
            src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1595594850091&di=449a96212ce98fa028c29494e64535c5&imgtype=0&src=http%3A%2F%2Fimg3.imgtn.bdimg.com%2Fit%2Fu%3D1590662363%2C713073460%26fm%3D214%26gp%3D0.jpg"
          />
        </div>
        <div class="footer-item footer-center">
          <dv-border-box-9 class="footer-center-ele">历史业绩</dv-border-box-9>
        </div>
        <div class="footer-item footer-right">
          <dv-decoration-1 style="width:200px;height:50px;" />
          <img src="https://www.ditingai.com/skin/assets/common/images/dt-logo.png">
          <dv-decoration-1 style="width:200px;height:50px;" />
        </div>
      </div>
    </dv-border-box-10>
  </div>
</template>

<script>
export default {
  name: 'BottomFooter'
}
</script>

<style lang="less">
#bottom-footer {
  position: relative;
  height: 200px;
  padding: 4px;
  display: flex;
  justify-content: space-between;
  flex-shrink: 0;
}
.footer {
  display: flex;
  height: 100%;
  &-item {
    flex: 1;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  &-left {
    justify-content: space-around;
  }
  &-center {
    &-ele {
      height: 80px;
      width: 200px;
      text-align: center;
      line-height: 80px;
      font-size: 30px;
    }
  }
  &-right {
    > img {
      width: 140px;
      height: 140px;
    }
  }
}
</style>
