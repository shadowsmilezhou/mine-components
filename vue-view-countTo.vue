<template>
  <div>
    <CountTo ref="countTo" @input='handleinput' :end-val='endVal'></CountTo>
    <button @click="getInnerNum">点我获取</button>
  </div>
</template>


<script>
import CountTo from './vue-countTo.vue'
import { parse } from 'path';
export default {
  data(){
    return {
      data:0,
      endVal:100
    }
  },
  components:{
    CountTo
  },
  methods:{
    handleinput(val){
      console.log(val)
      if(!val.length){
        this.endVal = 0      
      }else{
        this.endVal = val && parseInt(val)
      }   
    },
    getInnerNum(){
      console.log(this.$refs.countTo.getCount())
    }
  }
}
</script>


<style>

</style>
