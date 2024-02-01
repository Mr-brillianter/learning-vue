<script >
import comp_test from "./components/comp_test.vue";

export default{
  data(){
    return{
      msg:'神奇的语法'+'sad',
      
    }
  },
  components:{comp_test}
}
</script>

<template>
<p>{{ msg}}</p>
<comp_test/>
</template>

<style >

</style>
