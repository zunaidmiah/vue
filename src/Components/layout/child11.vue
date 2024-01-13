<template>
    <hr><hr>
    <div class="">
        <h1>I'm from 2nd level child</h1>
        <h2>{{ userName }}</h2>
        <Child111/>
    </div>
    <hr>
</template>

<script>
 import Child111 from './child111.vue';
    export default{
        data(){
            return[];
        },
        components: {
            'Child111': Child111,
        },
        inject:['userName'],

    }
</script>

<style>

</style>