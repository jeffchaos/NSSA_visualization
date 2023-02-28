<template>
  <div>
    <Echart
      :options="options"
      id="gauge"
      height="480px"
      width="1850px"
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
  tooltip: {
    trigger: 'axis'
  },
  legend: {
    data: ['实际值', '预测值']
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
    data: ['0:00', '2:00', '4:00', '6:00', '8:00', '10:00', '12:00','14:00','16:00','18:00','20:00','22:00','24:00']
  },
  yAxis: {
    type: 'value'
  },
  series: [
    {
      name: '实际值',
      type: 'line',
      data: this.cdata.data1
    },
    {
      name: '预测值',
      type: 'line',
      data: this.cdata.data2
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
