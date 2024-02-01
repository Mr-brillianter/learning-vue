<template>
<button v-on:click="AddCount">{{ count }}这里</button>
</template>

<script>
export default{
    data(){
        return{
            count:0
        }
    },
    methods:{
        AddCount(){
        this.count++
    }
    }
}
</script>

