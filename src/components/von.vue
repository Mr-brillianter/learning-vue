<template>
<button v-on:click="count++">{{ count }}这里</button>
<div>{{ count }}这里</div>
</template>

<script>
export default{
    data(){
        return{
            count:0
        }
    }
}
</script>

