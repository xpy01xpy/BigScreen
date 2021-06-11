<!--
 * @Author: xpy
 * @Description: 
 * @Date: 2021-06-10 19:11:47
 * @LastEditTime: 2021-06-11 11:39:43
-->
<template>
  <div :class="typeAttr">
    <slot></slot>
    <div v-if="type==='A'" class="bottom-border"></div>
  </div>
</template>

<script>
export default {
  name:'div-borders',
  props:{
    type:{
      type:String,
      default:'C',
    }
  },
  computed:{
    typeAttr(){
      return this.type==="A"?'border-warpper':'border-warpper2'
    }
  }
}
</script>

<style scoped>
.border-warpper{
  position: relative;
  box-sizing: border-box;
  border: .0125rem solid rgba(25, 186, 139, 0.17);
  margin: .125rem;
  min-height: 3.75rem;
  max-height: 3.875rem;
  padding: .125rem;
  overflow: hidden;
}
.border-warpper::before{
  content: "";
  display: block;
  width: .25rem;
  height: .125rem;
  border-left: .025rem solid rgba(25, 186, 139);
  border-top: .025rem solid rgba(25, 186, 139);

  position: absolute;
  top: 0;
  left: 0;
}
.border-warpper::after{
  content: "";
  display: block;
  width: .25rem;
  height: .125rem;
  border-right: .025rem solid rgba(25, 186, 139);
  border-top: .025rem solid rgba(25, 186, 139);

  position: absolute;
  top: 0;
  right: 0;
}
/* 中间部分 */
.border-warpper2{
  position: relative;
  border: .0125rem solid rgba(25, 186, 139, 0.17);
  margin: .125rem;
}


.bottom-border{
  position: absolute;
  height: .125rem;
  width: 100%;
  bottom: 0;
  left: 0;
}
.bottom-border::before{
  content: "";
  display: block;
  width: .25rem;
  height: .125rem;
  border-left: .025rem solid rgba(25, 186, 139);
  border-bottom: .025rem solid rgba(25, 186, 139);

  position: absolute;
  left: 0;
  bottom: 0;
}
.bottom-border::after{
  content: "";
  display: block;
  width: .25rem;
  height: .125rem;
  border-right: .025rem solid rgba(25, 186, 139);
  border-bottom: .025rem solid rgba(25, 186, 139);

  position: absolute;
  right: 0;
  bottom: 0;
}
</style>