<template>
  <div id="visual_two">
    <datav />
  </div>
</template>

<script>
import datav from '@/components/data_two/index.vue'
export default {
  name: 'VisualTwo',
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
#visual_two {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  width: 100%;
  height: 100%;
}
</style>

