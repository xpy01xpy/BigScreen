<!--
 * @Author: xpy
 * @Description: 内容
 * @Date: 2021-06-09 17:40:28
 * @LastEditTime: 2021-06-10 20:14:30
-->
<template>
  <div class="content-warpper">
    <!-- left -->
    <div class="content-left">
      <div-borders type="A">
        <charts-a></charts-a>
      </div-borders>
      <div-borders type="A">
        啊啊啊啊b
      </div-borders>
      <div-borders type="A">
        啊啊啊啊c
      </div-borders>
    </div>

    <!-- center -->
    <div class="content-center">
      <div-borders type="B">
        啊啊啊啊
      </div-borders>
    </div>

    <!-- right -->
    <div class="content-right">
      <div-borders>
        啊啊啊啊
      </div-borders>
    </div>
  </div>
</template>

<script>
import divBorders from './div-borders';
import A from './charts/A'

export default {
  name:"page-content",
  components:{
    "div-borders":divBorders,
    "charts-a":A,
  },
}
</script>

<style scoped>
.content-warpper{
  box-sizing: border-box;
  height: 12.25rem;
  display: flex;
  justify-content: space-between;
}
.content-warpper > div{
  box-sizing: border-box;
  height: 100%;
}
.content-left{
  min-width: 5.75rem;
}
.content-center{
  min-width: 12.5rem;
}
.content-right{
  min-width: 5.75rem;
}
</style>