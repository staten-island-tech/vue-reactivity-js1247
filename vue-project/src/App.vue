<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <header>Snack Shop</header>
  <RouterLink class="router" to="/">Shop</RouterLink>
  <RouterLink class="router" to="/checkout">Checkout</RouterLink>
  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
  text-align: center;
  font-size: 75px;
}
.router {
  text-decoration: none;
  padding: 15px 20px;
  margin: 20px;
  background-color: rgb(197, 197, 175);
  border: none;
  border-radius: 5px;
  font-size: 18px;
  font-weight: bold;
  cursor: pointer;
  transition: color 0.3s;
}
.router:hover {
  color: #ffffff;
}
</style>