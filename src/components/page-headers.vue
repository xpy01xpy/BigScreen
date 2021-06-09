<!--
 * @Author: xpy
 * @Description: 
 * @Date: 2021-06-09 15:45:57
 * @LastEditTime: 2021-06-09 17:07:40
-->
<template>
  <div class="headers-warpper">
    {{titleText}}
    <div class="header-time">
      {{date}}
    </div>
  </div>
</template>

<script>
import moment from 'moment'
export default {
  name:"page-headers",
  data(){
    return {
      titleText:'Data Visualization',
      date: moment(new Date()).format("YYYY-MM-DD HH:mm:ss"),
    }
  },
  created() {
    this.date = moment(new Date()).format("YYYY-MM-DD HH:mm:ss")
    // new Date()
  },
  watch:{
    date(newDate,oldDate){
      console.log(`newDate`, newDate)
      console.log(`oldDate`, oldDate)
      this.timer = setInterval(this.getNewDate,1000);
    }
  },
  methods: {
    getNewDate(){
      clearInterval(this.timer)
      this.date = moment(new Date()).format("YYYY-MM-DD HH:mm:ss");
    }
  },
}
</script>

<style scoped>
.headers-warpper{
  height: 1.25rem;
  width: 100%;
  color: #ffffff;
  font-size: .625rem;
  font-weight: 500;
  line-height: 1.125rem;
  background: url(https://nichan-13.github.io/Echarts-Demo/images/head_bg.png) no-repeat;
  background-size: 24rem 1.25rem;
  text-align: center;
  position: relative;
}
.header-time{
  position: absolute;
  top: 0;
  right: 0;

  border: 1px solid red;
  line-height: 1.125rem;
  height: 1.25rem;
  width: auto;
  min-width: 1.25rem;
}
</style>