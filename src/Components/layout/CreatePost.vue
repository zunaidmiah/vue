<template lang="">
    <div class="mb-2 p-4" style="border:1px solid gray;">
        <form @submit.prevent="CreatePost">
            <div class="pb-2">
                <label for="userId">User Id</label>&nbsp
                <input type="text" id="userId" v-model="data.userId">
            </div>

            <div class="pb-2">
                <label for="post-title">Post Title</label>&nbsp
                <input type="text" id="post-title" v-model="data.title">
            </div>

            <div class="pb-2">
                <label for="post-body">Post Body </label>&nbsp
                <input type="text" id="post-body" v-model="data.body">
            </div>

            <div class="pb-2">
                <button class="btn btn-primary">Submit</button>
            </div>
        </form>
    </div>
</template>
<script>
import axios from 'axios'
export default {
    data(){
        return{
            data:{
                userId:'',
                title:'',
                body:''
            }
        }
    },
    methods:{
        CreatePost(){
            console.log("submitted")
            axios.post('https://jsonplaceholder.typicode.com/posts', this.data)
                .then((res) => {
                    console.log(res)
                })
                .catch((err) => {
                    console.log(err)
                })
        }
    }
}
</script>
<style lang="">
    
</style>