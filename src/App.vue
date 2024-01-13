<template>
    <mainHeader></mainHeader>
    <div  class="container p-4 m-4">
        <h1>{{ name }}</h1>
        <h2>{{ Age }}</h2>
        <h3>{{ Girlfriend }}</h3>
        <button @click="makeLove">Love</button>
        <Child1/>
        <Table></Table>
        <Form></Form>
        <mainFooter :name="name"></mainFooter>
    </div>
</template>

<script>
    import Header from './Components/main/header.vue';
    import Footer from './Components/main/footer.vue';
    import Table from './Components/layout/table.vue';
    import Form from './Components/layout/form.vue';
    import Child1 from './Components/layout/child1.vue';
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
                if(this.name == 'Zunaid Miah'){
                    this.name=this.name +"+"+ this.Girlfriend;
                }
            }
        },

        components:{
            'mainHeader' : Header,
            'mainFooter' : Footer,
            'Table' : Table,
            'Form' : Form,
            'Child1' : Child1,
        },

        provide(){
            return{
                userName: this.name,
                Age: this.Age,
            }
        }
    }
</script>