<template>
  <div>
    <Chart :cdata="cdata" />
  </div>
</template>

<script>
// import Chart from './chart.vue';
import Chart from './chart.vue';
export default {
  data () {
    return {
      cdata: {
        xData: ["data1", "data2", "data3", "data4", "data5"],
        seriesData: [
          { value: 10, name: "DDOS攻击" },
          { value: 5, name: "数据库攻击" },
          { value: 15, name: "端口扫描" },
          { value: 25, name: "DNS隧道" },
          { value: 20, name: "WIFI接入" }
        ]
      }
    }
  },
  components: {
    Chart,
  },
  mounted () {
    this.setData()
  },
  methods: {
    setData () {
      this.$axios.get('http://localhost:8080/static/page2.json').then(res=>{
        this.cdata = res.data.gauge
      })
    }
  }
}
</script>

<style lang="scss" scoped>
</style>