<template>
<div class="Hook">
    <h1>Posts</h1><hr>
    <input type="text" v-model="searchTerm" >
    <div v-for="post in filterseacrh" :key="post.id">
        <h2>{{post.title}}</h2>
        <p>{{post.body | snippet}}</p><hr>
    </div>
</div>
</template>

<script>
import axios from'axios'
export default {
    name:'Hook',
    data(){
        return{
           posts:[],
           searchTerm: ''
        }
    },
    computed:{
        filterseacrh(){
          return  this.posts.filter(post =>{
                return post.title.match(this.searchTerm)
            })
        }
    },
    methods:{
      
    },
    created(){
        axios.get('https://jsonplaceholder.typicode.com/posts')
        .then(response =>{
            //console.log(response)
            this.posts =response.data
        })
        .catch(error =>{
            console.log(error)
        })
    }
   

}
</script>

<style >
h1{
    color: red;
    text-align: center;
}

</style>


