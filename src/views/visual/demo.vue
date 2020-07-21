<template>
  <div id="visual_demo">
    <datav />
  </div>
</template>

<script>
import datav from '@/components/data_demo/index.vue'
export default {
  name: 'VisualDemo',
  components: {
    datav
  },
  data() {
    return {}
  },

  methods: {}
}
</script>

<style lang="scss" scoped>
#visual_demo {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  width: 100%;
  height: 100%;
}
</style>

