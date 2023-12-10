<template>
    <h1>Catalog</h1>
</template>

<script>
    import { defineComponent } from 'vue';

    export default defineComponent ({
        name: 'CatalogView'
    });
</script>

<script setup>
    import { onMounted } from 'vue';

    onMounted(() => {
        console.log('onMounted');
    })
</script>

<style>

</style>