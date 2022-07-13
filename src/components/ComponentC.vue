<template>
<div>
    Component C
</div>
    <ComponentD />
</template>

<script>
import ComponentD from "./ComponentD.vue";
    export default {
        name: 'ComponentB',
        components: {
            ComponentD
        }
    }
</script>

<style scoped>

</style>