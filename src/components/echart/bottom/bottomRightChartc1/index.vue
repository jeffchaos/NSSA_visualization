<template>
  <div>
    <Chart :cdata="cdata" />
  </div>
</template>

<script>
import Chart from './chart.vue'
export default {
  data () {
    return {
      drawTiming: null,
      cdata: {
        // xdata: null,
        // seriesf: [],
        // seriess: [],
        // radarDataAvg: [],
        // maxData: 12000,
        // weekMaxData: [],
        // weekLineData: []
      }
    }
  },
  components: {
    Chart,
  },
  mounted () {
    this.drawTimingFn();
  },
  beforeDestroy () {
    clearInterval(this.drawTiming);
  },
  methods: {
    drawTimingFn () {
      this.setData();
      this.drawTiming = setInterval(() => {
        this.setData();
      }, 6000);
    },
    setData () {
      this.$axios.get('http://localhost:8080/static/page1.json').then(res=>{
        this.cdata = res.data.device.second
      })
    }
  }
};
</script>

<style lang="scss" scoped>
</style>