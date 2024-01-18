<template lang="">
    <Header/>
    <div class="container p-4 m-4" style="min-height:600px;">
        <CreatePost/>
        <PostLists/>
    </div>
    <Footer/>
</template>
<script>
import Header from './Components/main/header.vue';
import Footer from './Components/main/footer.vue';
import PostLists from './Components/layout/PostLists.vue';
import CreatePost from './Components/layout/CreatePost.vue';
export default {
    components:{
        Header,
        Footer,
        PostLists,
        CreatePost
    }
}
</script>
<style lang="">
    
</style>