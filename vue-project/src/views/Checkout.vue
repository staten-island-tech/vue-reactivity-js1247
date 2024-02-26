<template>
  <div class="checkout">
    <h1>This is the checkout page</h1>
    <ShoppingCart
      v-for="item in snacks"
      :name="item.name"
      :type="item.type"
      :price="item.price"
      :image="item.image"
    ></ShoppingCart>
  </div>
</template>
<script setup>
import ShoppingCart from "@/components/ShoppingCart.vue";
import { snacks } from "@/stores/array.js";
</script>

<style scoped></style>
