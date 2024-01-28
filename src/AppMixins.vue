<template>
    <Header/>
    <Mixins1/>
    <Mixins2/>
    <Footer/>
</template>
<script>
import Header from './Components/main/header.vue'
import Footer from './Components/main/footer.vue'
import Mixins1 from './Components/mixins/mixins1.vue'
import Mixins2 from './Components/mixins/mixins2.vue'
export default {
    data(){
        return{
            count: 0
        }
    },
    methods:{
        IncremnetClickNumber(){
            this.count += 1;
        }

    },
    components:{
        Header,
        Footer,
        Mixins1,
        Mixins2,
    }
}
</script>
<style>
    
</style>