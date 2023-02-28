<template>
  <div id="centerRight1">
    <div class="bg-color-black">
      <div class="d-flex pt-2 pl-2">
        <span>
          <icon name="chart-line" class="text-icon"></icon>
        </span>
        <div class="d-flex">
          <span class="fs-xl text mx-2">设备权重列表</span>
        </div>
      </div>
      <div class="d-flex jc-center body-box">
        <dv-scroll-board class="dv-scr-board" :config="config"  style="width:700px;height:340px" />
      </div>
    </div>
  </div>
</template>

<script>


export default {
  data() {
    return {
      config: {
        header: ['主机序号', '主机IP', '开放服务数','主机权重'],
        data: [
          ["hy122", '192.168.1.8','5','5'],
          ["hy123", '192.168.1.8','12','4'],
          ["hy124", '192.168.1.8','34','3'],
          ["hy125", '192.168.1.8','13','2'],
          ["hy126", '192.168.1.8','15','1'],
          ["hy127", '192.168.1.8','16','1'],
        ],
        rowNum: 5, //表格行数
        headerHeight:30,
        headerBGC: '#0f1325', //表头
        oddRowBGC: '#0f1325', //奇数行
        evenRowBGC: '#171c33', //偶数行
        index: true,
        columnWidth: [50,120,260,120,80],
        align: ['center','center','center','center']
      }
    }
  },
  mounted(){
    this.getData()
  },
  methods:{
    getData(){
      this.$axios.get('http://localhost:8080/static/page1.json').then(res=>{
        this.config.data = res.data.weightValue.data
        this.$set( this.config, this.config.data, res.data.weightValue.data )
      })
    }
  }

}
</script>

<style lang="scss" scoped>
$box-height: 420px;
$box-width: 670px;
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
