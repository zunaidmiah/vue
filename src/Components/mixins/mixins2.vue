<template>
    <div class="container mt-4">
        <button @mouseover="IncremnetClickNumber">Hovered {{ count }} times</button>
    </div>
</template>
<script>
import Mixins from '../../mixins.js'
export default {
    data(){
        return{
            count:10,
        }
    },
    mixins:[Mixins],
    methods:{
        IncremnetClickNumber(){
            this.count += 5;
        }

    },
    components:{
        
    }
}
</script>
<style>
    
</style>