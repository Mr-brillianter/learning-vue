<!-- 组件导入测试 -->
<script >
export default{
  data(){
    return{
      msg2:'这是一个组件'
    }
  }
}
</script>

<template>
<div class="myclassfont1">{{ msg2}}</div>
</template>

<style >
.myclassfont1{
  font-size: 12px;
  color:blueviolet
}
</style>
