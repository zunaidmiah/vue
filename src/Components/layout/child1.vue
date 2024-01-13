<template>
    <hr><hr>
    <div class="container p-4 m-4">
        <h1>I'm from 1st level child</h1>
        <Child11/>
    </div>
    <hr>
</template>

<script>
    import Child11 from './child11.vue';
    export default{
        data(){
            return[];
        },
        components: {
            'Child11': Child11,
        }

    }
</script>

<style>

</style>