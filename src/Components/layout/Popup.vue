<template lang="">
    <div>
        <h2>This is a Popup</h2>
        <button @click="$emit('closePopup', 'Zunaid', 'Miah')" class="btn btn-danger">Close Popup</button>
    </div>
</template>
<script>
export default {
    emits:['closePopup'],
}
</script>
<style lang="">
    
</style>