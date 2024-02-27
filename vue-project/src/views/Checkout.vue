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

</script>

<style scoped></style>
