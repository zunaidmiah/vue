<template lang="">
    <div>
        <button class="btn btn-info" @click="getPosts">Get Posts</button>
        <hr>
        <div v-for="item in data" :key="item.id">
            <h3>Title: {{ item.title }}</h3>
            <p>{{ item.body }}</p>
            <hr>
        </div>
    </div>
</template>
<script>
import axios from 'axios'
export default {
    data(){
        return{
            data:[]

        }
    },
    methods:{
        getPosts(){
            console.log("clicked button")
            axios.get('https://jsonplaceholder.typicode.com/posts')
                .then((res) => {
                    console.log(res.data)
                    this.data = res.data
                    
                })
                .catch((err) => {

                })
        }
    }
}
</script>
<style lang="">
    
</style>