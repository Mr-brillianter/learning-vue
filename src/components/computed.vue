<!-- 计算属性 -->
<template>
<h3>{{ msg.name }}</h3>
<p>{{ msg.content.length>0?"Yes":"No" }}</p>
<p>{{ msg_has_content}}</p>

</template>

<script>
export default{
    data(){
        return{
            msg:{
                name:"这是一个类似于类的东西",
                content:["Python","Java","C"]
            }
        }
    },
    computed:{ //标准格式
        msg_has_content(){ //新变量名
            return this.msg.content.length>0?"Yes":"No" // 记得加this.
        }
    }
}
</script>