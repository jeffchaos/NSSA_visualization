<template>
  <div>
    <Chart :cdata="cdata" />
  </div>
</template>

<script>
import Chart from './chart.vue';
export default {
  data () {
    return {
      cdata: {
        
      }
    }
  },
  methods:{
    getData(){
      this.$axios.get('http://localhost:8080/static/page1.json').then(res=>{
        this.cdata = res.data.attack
      })
    },
  },
  mounted(){
    this.getData()
  },
  components: {
    Chart,
  }
}
</script>