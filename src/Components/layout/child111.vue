<template>
    <hr><hr>
    <div class="">
        <h1>I'm from 3rd level child</h1>
        <h3>{{ userName }}</h3>
        <h3>{{ Age }}</h3>
    </div>
    <hr>
</template>

<script>
 export default{
    inject: ['userName', 'Age'],
 }
</script>

<style>

</style>