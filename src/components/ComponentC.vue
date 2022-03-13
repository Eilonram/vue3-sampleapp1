<template>
    <h2>Component C</h2>
    <component-e />
</template>

<script>
import ComponentE from './ComponentE.vue'
    export default {
        name: 'ComponentC',
        components: {
            ComponentE
        }
    }
</script>

<style scoped>

</style>