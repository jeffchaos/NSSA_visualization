<template>
  <div id="centerRight1">
    <div class="bg-color-black">
      <div class="d-flex pt-2 pl-2">
        <span>
          <icon name="chart-line" class="text-icon"></icon>
        </span>
        <div class="d-flex">
          <span class="fs-xl text mx-2">来源</span>
        </div>
      </div>
      <div class="d-flex jc-center body-box" style="font-size: 20px;">
        <dv-scroll-board class="dv-scr-board" :config="config"  style="width:1500px;height:320px" />
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data() {
    return {
      config: {
        header: ['时间', '来源', '详情'],
        data: [
          ["2023-02-12 17:23:12", '192.168.1.8','已处理'],
          ["2023-02-12 17:23:12", '192.168.1.8','已处理'],
          ["2023-02-12 17:23:12", '192.168.1.8','已处理'],
          ["2023-02-12 17:23:12", '192.168.1.8','已处理'],
          ["2023-02-12 17:23:12", '192.168.1.8','已处理'],
          ["2023-02-12 17:23:12", '192.168.1.8','已处理']
         
        ],
        rowNum: 5, //表格行数
        headerHeight: 70,
        headerBGC: '#0f1325', //表头
        oddRowBGC: '#0f1325', //奇数行
        evenRowBGC: '#171c33', //偶数行
        index: true,
        columnWidth: [240,320,220,540],
        align: ['center','center','center','center']
      }
    }
  },
  mounted(){
    this.getData()
  },
  methods:{
    getData(){
      this.$axios.get('http://localhost:8080/static/page2.json').then(res=>{
        this.config.data = res.data.source.data
        this.$set( this.config, this.config.data, res.data.source.data )
      })
    }
  }

}
</script>

<style lang="scss" scoped>
$box-height: 380px;
$box-width: 1240px;
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
      width: 670px;
      height: 340px;
    }
  }
}
</style>
