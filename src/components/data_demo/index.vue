<template>
  <div id="data-view">
    <dv-full-screen-container>
      <top-header />
      <content-content />
      <bottom-footer />
    </dv-full-screen-container>
  </div>
</template>

<script>
import topHeader from './topHeader'
import bottomFooter from './bottomFooter'
import contentContent from './content'

export default {
  name: 'DataView',
  components: {
    topHeader,
    bottomFooter,
    contentContent
  },
  data() {
    return {}
  },
  methods: {}
}
</script>

<style lang="less">
#data-view {
  width: 100%;
  height: 100%;
  background-color: #030409;
  color: #fff;

  #dv-full-screen-container {
    background-image: url('./img/bg.png');
    background-size: 100% 100%;
    box-shadow: 0 0 3px blue;
    display: flex;
    flex-direction: column;
  }
}
</style>
