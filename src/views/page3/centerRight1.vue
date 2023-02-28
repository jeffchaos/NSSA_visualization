<template>
  <div id="centerRight1">
    <div class="bg-color-black">
      <div class="d-flex pt-2 pl-2">
        <span>
          <icon name="chart-line" class="text-icon"></icon>
        </span>
        <div class="d-flex">
          <span class="fs-xl text mx-2">来源统计</span>
        </div>
      </div>
      <div class="d-flex jc-center body-box" style="font-size: 20px;">
        <dv-scroll-board class="dv-scr-board" :config="config"  style="width:1900px;height:320px" />
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data() {
    return {
      config: {
        header: ['时间', '源IP', '源端口','IP地理位置','规则号','攻击信息','攻击类型','危险等级','方法'],
        data: [
          ["2023-01-11 15:18:01","192.168.2.8","50806","印度","102","非法探测，可能为下一步攻击准备","恶意漏洞探测","<span class='colorRed'>高</span>", 'GET'],
          ["2023-01-11 15:18:02","192.168.2.8","50806","印度","102","非法探测，可能为下一步攻击准备","恶意漏洞探测","<span class='colorRed'>高</span>", 'GET'],
          ["2023-01-11 15:18:01","192.168.2.8","50806","印度","102","非法探测，可能为下一步攻击准备","恶意漏洞探测","<span class='colorRed'>高</span>", 'GET'],
          ["2023-01-14 15:18:01","192.168.2.8","50806","印度","102","非法探测，可能为下一步攻击准备","恶意漏洞探测","<span class='colorRed'>高</span>", 'GET'],
          ["2023-01-11 15:18:01","192.168.2.8","50806","印度","102","非法探测，可能为下一步攻击准备","恶意漏洞探测","<span class='colorRed'>高</span>", 'GET']
         
        ],
        rowNum: 5, //表格行数
        headerHeight: 70,
        headerBGC: '#0f1325', //表头
        oddRowBGC: '#0f1325', //奇数行
        evenRowBGC: '#171c33', //偶数行
        index: true,
        columnWidth: [100,220,120,120,120,200,400,200,200,200],
        align: ['center','center','center','center','center','center','center','center','center']
      }
    }
  },
  mounted(){
    this.getData()
  },
  methods:{
    getData(){
      this.$axios.get('http://localhost:8080/static/page3.json').then(res=>{
        this.config.data = res.data.table
        this.$set( this.config, this.config.data, res.data.table )
      })
    }
  }
}
</script>

<style lang="scss" scoped>
$box-height: 380px;
$box-width: 1890px;
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
