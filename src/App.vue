<template>
  <header>
    <div class="cart-items border p-2" @click="router.push({name: 'CartView'})">
      <p class="p-2 m-0">Items in Cart: {{ store.cart.length }}</p>
    </div>
  </header>
  <main>
    <RouterView />
  </main>
</template>

<script setup>
  import { useRouter } from "vue-router";
  import { productsStore } from "@/stores/products";

  const router = useRouter();
  const store = productsStore();

</script>

<style scoped>
  .cart-items {
    text-align: end;
    padding: 16px;
    font-weight: bold;
    font-size: 24px;
    cursor: pointer;
  }
</style>
