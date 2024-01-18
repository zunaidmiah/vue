<template>
    <div style="border:0.5px solid gray;">
        <h1>This is Footer, @Copyright reserved for {{ name }}</h1>
    </div>
</template>

<script>
   export default{
    props:['name']
   };
</script>
<style scoped>
 h1{
     color: red;
 }
</style>