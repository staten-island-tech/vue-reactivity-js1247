<template>
  <div class="checkout">
    <h1>This is the checkout page</h1>
    <Checkout
      v-for="item in items"
      :name="item.name"
      :type="item.type"
      :price="item.price"
      :image="item.image"
    />
  </div>
</template>
<script setup>
import { items } from "@/components/Checkout.vue"
</script>

<style scoped>
</style>
