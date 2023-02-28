<template>
  <div id="centerRight1">
    <div class="bg-color-black">
      <div class="d-flex pt-2 pl-2">
        <span>
          <icon name="chart-line" class="text-icon"></icon>
        </span>
        <div class="d-flex">
          <span class="fs-xl text mx-2">被攻击主机TOP5</span>
        </div>
      </div>
      <div class="d-flex jc-center">
        <CenterRight1Chart />
      </div>
      <!-- <div class="d-flex jc-center body-box">
        <dv-scroll-board class="dv-scr-board" :config="config"  style="width:700px;height:400px" />
      </div> -->
    </div>
  </div>
</template>

<script>
import CenterRight1Chart from '@/components/echart/centerRightb/centerRightChartb'


export default {
  components: {
    CenterRight1Chart
  },
  data() {
    return {
    }
  }
}
</script>

<style lang="scss" scoped>
$box-height: 380px;
$box-width: 650px;
#centerRight1 {
  padding: 16px;
  padding-top: 20px;
  height: $box-height;
  width: $box-width;
  border-radius: 5px;
  .bg-color-black {
    height: $box-height - 30px;
    border-radius: 10px;
  }
  .text {
    color: #c3cbde;
  }
  .body-box {
    border-radius: 10px;
    overflow: hidden;
    .dv-scr-board {
      width: 270px;
      height: 340px;
    }
  }
}
</style>
