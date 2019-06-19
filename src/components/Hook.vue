<template>
<div class="Hook">
    <h1>{{title}}</h1>
    <button @click="changeTitle">click me</button>
</div>
</template>

<script>
export default {
    name:'Hook',
    data(){
        return{
            title:'Hook Part'
        }
    },
    methods:{
        changeTitle(){
            this.title = 'learn huter'
        }
    },
    beforeCreate(){
        alert('before acreated hook')
    },
    created(){
        alert('created hook')
    },
    beforeUpdate(){
        alert('before Update')
    },
    updated(){
        alert('update')
    }

}
</script>

<style >


</style>


