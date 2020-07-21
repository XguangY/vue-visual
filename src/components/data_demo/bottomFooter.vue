<template>
  <div id="bottom-footer">
    <dv-border-box-10>
      <div class="center-title">谛听股票操盘手</div>
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
  width: 100%;
  height: 200px;
  padding: 4px;
  display: flex;
  justify-content: space-between;
  flex-shrink: 0;
  .center-title {
    position: absolute;
    font-size: 30px;
    font-weight: bold;
    left: 50%;
    top: 15px;
    transform: translateX(-50%);
  }
}
</style>
