<template>
    <div>
        <mainHeader></mainHeader>
        <h1>{{ name }}</h1>
        <h2>{{ Age }}</h2>
        <h3>{{ Girlfriend }}</h3>
        <button @click="makeLove">Love</button>
        <mainFooter></mainFooter>
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
        methods:{
            makeLove(){
                this.name=this.name +"+"+ this.Girlfriend;
            }
        },
        components:{
            'mainHeader' : Header,
            'mainFooter' : Footer
        }
    }
</script>