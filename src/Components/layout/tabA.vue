<template lang="">
    <div class="p-4">
        Tab A content
        <input type="text" placeholder="Enter Your Name" v-model="name"/>
    </div>
</template>
<script>
export default {
    data(){
        return{
            name: '',
        };
    }
}
</script>
<style lang="">
    
</style>