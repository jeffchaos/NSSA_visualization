<template>
  <div id="centerRight1">
    <div class="bg-color-black">
      <div class="d-flex pt-2 pl-2">
        <span>
          <icon name="chart-line" class="text-icon"></icon>
        </span>
        <div class="d-flex">
          <span class="fs-xl text mx-2">事件监控</span>
        </div>
      </div>
      <div class="d-flex jc-center body-box">
        <dv-scroll-board class="dv-scr-board" :config="config"  style="width:700px;height:300px" />
      </div>
    </div>
  </div>
</template>

<script>


export default {
  data() {
    return {
      config: {
        header: ['等级', '事件类型', '主机IP','威胁源IP','状态'],
        data: [
          ["<span class='colorGreen'>低</span>", '端口扫描', '192.168.1.8','48.12.1.2','已处理'],
          ["<span class='colorYellow'>中</span>", 'DNS隧道', '192.168.1.8','48.12.1.2','已处理'],
          ["<span class='colorRed'>高</span>", '数据库攻击', '192.168.1.8','48.12.1.2','已处理'],
          ["<span class='colorGreen'>低</span>", '端口扫描', '192.168.1.8','48.12.1.2','已处理'],
          ["<span class='colorRed'>高</span>", '数据库攻击', '192.168.1.8','48.12.1.2','已处理'],
        ],
        rowNum: 5, //表格行数
        headerHeight: 20,
        headerBGC: '#0f1325', //表头
        oddRowBGC: '#0f1325', //奇数行
        evenRowBGC: '#171c33', //偶数行
        index: true,
        columnWidth: [50,120,120,140,140,80],
        align: ['center','center','center','center','center']
      }
    }
  },
  mounted(){
    this.getData()
  },
  methods:{
    getData(){
      this.$axios.get('http://localhost:8080/static/page1.json').then(res=>{
        this.config.data = res.data.thingsMonitor.data
        this.$set( this.config, this.config.data, res.data.thingsMonitor.data )
      })
    }
  }
}
</script>

<style lang="scss" scoped>
$box-height: 380px;
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
