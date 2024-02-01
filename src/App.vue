<script >
import comp_test from "./components/comp_test.vue";
import vif from "./components/vif.vue";
export default{
  data(){
    return{
      msg:'神奇的语法'+'sad',
      
    }
  },
  components:{comp_test,vif}
}
</script>

<template>
<p>{{ msg}}</p>
<vif/>
<comp_test/>
</template>

<style >

</style>
