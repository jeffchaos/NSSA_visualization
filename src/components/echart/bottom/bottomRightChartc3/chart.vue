<template>
  <div>
    <Echart
      :options="options"
      id="centreLeft1Chart"
      height="180px"
      width="550px"
    ></Echart>
  </div>
</template>

<script>
import Echart from '@/common/echart'

export default {
  
  data() {
    return {
      options: {}
    }
  },
  components: {
    Echart
  },
  props: {
    cdata: {
      type: Object,
      default: () => ({})
    }
  },
  watch: {
    cdata: {
      
      handler(newData) {
        console.log(newData)
        this.options = {
  title: {
    text: this.cdata.name
  },
  tooltip: {
    trigger: 'axis'
  },
  legend: {
    data: ['CPU占用率(%)', '内存占用率(%)', '带宽占用率(%)']
  },
  grid: {
    left: '3%',
    right: '4%',
    bottom: '3%',
    containLabel: true
  },
  toolbox: {
    feature: {
      saveAsImage: {show:false}
    }
  },
  xAxis: {
    type: 'category',
    boundaryGap: false,
    data: this.cdata.xdata
  },
  yAxis: {
    type: 'value'
  },
  series: [
    {
      name: 'CPU占用率(%)',
      type: 'line',
      data: this.cdata.seriesf
    },
    {
      name: '内存占用率(%)',
      type: 'line',
      data: this.cdata.seriess
    },
    {
      name: '带宽占用率(%)',
      type: 'line',
      data: this.cdata.seriest
    }
  ]
}
      },
      immediate: true,
      deep: true
    }
  }
}
</script>
