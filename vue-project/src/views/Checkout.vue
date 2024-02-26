<template>
  <div class="checkout">
    <h1>This is the checkout page</h1>
    <CheckoutCard
      v-for="item in items"
      :name="item.name"
      :type="item.type"
      :price="item.price"
      :image="item.image"
    />
  </div>
</template>
<script setup>
import { items } from "@/components/CheckoutCard.vue"
</script>

<style scoped>
</style>
