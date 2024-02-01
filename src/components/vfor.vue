<template>

<h3>列表循环</h3>
<!-- html换行 -->
<br>

<div v-for="item in items">
{{ item }}
</div>

</template>

<script>
export default{
    data(){
        return{
            items:[1,2,3,4]
        }
    }
}
</script>

<style>
</style>