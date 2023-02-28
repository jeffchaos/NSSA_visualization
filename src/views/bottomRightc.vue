<template>
  <div id="bottomRight">
    <div class="bg-color-black">
      <div class="d-flex pt-2 pl-2">
        <span>
          <icon name="chart-area" class="text-icon"></icon>
        </span>
        <div class="d-flex">
          <span class="fs-xl text mx-2">设备运行情况</span>
          <div class="decoration2">
            <dv-decoration-2 :reverse="true" style="width:5px;height:6rem;" />
          </div>
        </div>
      </div>
     <div class="d-flex ">
      <div class="react-left">
        <span>
        <BottomRightChart />
        </span>
      <span>
        <BottomRightChart1/>
      </span>
      </div>
      <div class="react-right ml-3" >
        <span>
        <BottomRightChart2 />
      </span>
      <span>
        <BottomRightChart3 />
      </span>

      </div>

     </div>
    </div>
  </div>
</template>

<script>
import BottomRightChart from "@/components/echart/bottom/bottomRightChartc";
import BottomRightChart1 from "@/components/echart/bottom/bottomRightChartc1";
import BottomRightChart2 from "@/components/echart/bottom/bottomRightChartc2";
import BottomRightChart3 from "@/components/echart/bottom/bottomRightChartc3";
export default {
  components: {
    BottomRightChart,
    BottomRightChart1,
    BottomRightChart2,
    BottomRightChart3
  }
};
</script>

<style lang="scss" scoped>
$box-height: 420px;
$box-width: 100%;
#bottomRight {
  padding: 14px 16px;
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
  //下滑线动态
  .decoration2 {
    position: absolute;
    right: 0.125rem;
  }
  .chart-box {
    margin-top: 16px;
    width: 170px;
    height: 170px;
    .active-ring-name {
      padding-top: 10px;
    }
  }
}
</style>