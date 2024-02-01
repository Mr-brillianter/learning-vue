<template>
<button v-on:click="AddCount">{{ count }}这里</button>
<button v-on:click="AddCount2">你好</button>
</template>

<script>
export default{
    data(){
        return{
            count:0,
            count2:0
        }
    },
    methods:{
        AddCount(e){
            this.count++
            console.log(e)
    },
        AddCount2(e){
            this.count2++
            console.log(e.target.innerHTML)
            e.target.innerHTML=this.count2
    }
    }
}
</script>

