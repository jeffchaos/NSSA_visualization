<template>
  <div>
    <Echart
      :options="options"
      id="centreLeft1Chartb"
      height="320px"
      width="460px"
    ></Echart>
  </div>
</template>

<script>
import Echart from '@/common/echart'

export default {
  data () {
    return {
      options: {},
    };
  },
  components: {
    Echart,
  },
  props: {
    cdata: {
      type: Object,
      default: () => ({})
    },
  },
  watch: {
    cdata: {
      handler (newData) {
        this.options = {
          xAxis: {
    max: 'dataMax'
  },
  yAxis: {
    type: 'category',
    // data: ['A', 'B', 'C', 'D', 'E'],
    data: this.cdata.name,
    
    inverse: true,
    animationDuration: 300,
    animationDurationUpdate: 300,
    max: 4 // only the largest 3 bars will be displayed
  },
  series: [
    {
      realtimeSort: true,
      // name: 'X',
      type: 'bar',
      // data: cdata['5','4','3','2','1'],
      data: this.cdata.value,
      label: {
        show: true,
        position: 'right',
        valueAnimation: true
      }
    }
  ],
          tooltip: {
            trigger: "item",
            formatter: "{a} <br/>{b} : {c} ({d}%)"
          },
          toolbox: {
            show: false
          },
          calculable: true,
          legend: {
            orient: "horizontal",
            icon: "circle",
            bottom: 0,
            x: "center",
            data: newData.xData,
            textStyle: {
              color: "#fff"
            }
          }
        }
      },
      immediate: true,
      deep: true
    }
  }
};
</script>

<style lang="scss" scoped>
</style>