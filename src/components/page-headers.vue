<!--
 * @Author: xpy
 * @Description: 
 * @Date: 2021-06-09 15:45:57
 * @LastEditTime: 2021-06-09 17:37:03
-->
<template>
  <div class="headers-warpper">
    {{titleText}}
    <div class="header-time">
      当前时间：{{date}}
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
      date: ""
    }
  },
  created() {
    // 组件初始化赋值
    this.date = moment(new Date()).format("YYYY-MM-DD HH:mm:ss");
  },
  unmounted(){
    // 组件销毁 清除计时器 防止内存泄漏
    this.clearTimer()
  },
  watch:{
    date(){
      this.timer = setInterval(this.getNewDate,1000);
    }
  },
  methods: {
    getNewDate(){
      // 清除计时器
      this.clearTimer()
      // 更改最新值
      this.date = moment(new Date()).format("YYYY-MM-DD  HH:mm:ss");
    },
    clearTimer(){
      clearInterval(this.timer)
    },
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
  right: .625rem;
  font-size: .5rem;

  line-height: 1.125rem;
  height: 1.25rem;
  width: auto;
  min-width: 1.25rem;
}
</style>