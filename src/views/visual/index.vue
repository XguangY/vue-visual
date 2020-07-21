<template>
  <div id="visual">
    <datav />
  </div>
</template>

<script>
import datav from '@/components/datav/index.vue'
export default {
  name: 'Visual',
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
#visual {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  width: 100%;
  height: 100%;
}
</style>

