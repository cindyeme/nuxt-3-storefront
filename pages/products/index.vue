<template>
  <div>
    <div class="grid sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-5">
      <div v-for="p in products" :key="p.id">
        <product-card :product="p" />
      </div>
    </div>
  </div>
</template>

<script setup>
definePageMeta({
  layout: "products",
});

// fetch the products
const { data: products } = await useFetch("https://fakestoreapi.com/products");

useHead({
  title: "Nuxt Whisper | Products",
  meta: [{ name: "description", content: "List of products" }],
});
</script>

<style scoped></style>
