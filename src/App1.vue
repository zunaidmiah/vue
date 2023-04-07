<template>
    <div>
        <mainHeader1></mainHeader1>
        <h1>{{ name }}</h1>
        <h2>{{ Age }}</h2>
        <h3>{{ Girlfriend }}</h3>
        <mainFooter1></mainFooter1>
    </div>
</template>

<script>
    import Header from './Components/main/header.vue';
    import Footer from './Components/main/footer.vue';
    export default{
        data(){
            return {
                name:'Zunaid Miah',
                Age: 25,
                Girlfriend: 'Tithy'
            }
        },
        components:{
            'mainHeader1' : Header,
            'mainFooter1' : Footer
        }
    }
</script>