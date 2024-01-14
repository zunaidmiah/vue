<template>
    <div class="card mb-4 p-2" style="width: 18rem;">
        <div>
            <slot name="card-header"></slot> 
        </div>
        <div>
            <slot>Here From Default Content</slot> 
        </div>
        <div>
            <slot  name="card-footer"></slot> 
        </div>
    </div>
</template>
<script>
export default {
    
}
</script>
<style>
    
</style>