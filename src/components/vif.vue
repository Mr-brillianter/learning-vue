<template>
<div v-if="type=='A'">类型是A</div>
<div v-else-if="type=='B'">类型是B</div>
<div v-else-if="type=='C'">类型是C</div>
<div v-else>类型不是ABC</div>

</template>

<script>
export default{
    data(){
        return{
            type:'d'
        }
    }
}
</script>

<style>

</style>