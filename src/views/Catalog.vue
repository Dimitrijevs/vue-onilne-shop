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
    import { productsStore }  from "@/stores/products.js";

    const productStore = productsStore();

    onMounted(() => {
        console.log('onMounted')
        productStore.fetchProductsFromDB()
    })
</script>

<style>

</style>