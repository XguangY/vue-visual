<template>
  <div class="main-content">
    <div class="chart">
      <message />
      <core />
      <strategy />
    </div>
  </div>
</template>

<script>
import Message from '@/components/data_demo/message.vue'
import Core from '@/components/data_demo/core.vue'
import Strategy from '@/components/data_demo/strategy.vue'
export default {
  name: 'Content',
  components: {
    Message,
    Core,
    Strategy
  },
  data() {
    return {}
  },
  mounted() {},
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
  }
}
</style>
