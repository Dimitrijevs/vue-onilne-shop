<template>
    <div class="products-list">
        <div class="product" v-for="product in store.products" :key="product.id" @click="goToProductPage(product.id)">
            <img :src="product.thumbnail" alt="">
            <h2>Brand: {{ product.title }}</h2>
            <p>Description: {{ product.description }}</p>
            <p>Price: {{ product.price }} €</p>
        </div>
    </div>
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
    import { useRouter } from 'vue-router';

    const store = productsStore();
    const router = useRouter()

    const goToProductPage = (id) => {
        router.push({ name: 'ProductView', params: { id }})
    }

    onMounted(() => {
        console.log('onMounted')
        store.fetchProductsFromDB()
    })
</script>

<style scoped>
    .products-list {
        display: grid;
        grid-template-columns: repeat(3, auto);
        margin: 0 auto;
        grid-gap: 40px;
    }

    .product {
        cursor: pointer;
    }

    .product img {
        max-width: 240px;
    }
</style>