<template>
  <div class="card" v-for="snack in snacks">
    <h1 class="name">{{ snack.name }}</h1>
    <img :src="snack.image" :alt="snack.name" class="snack-image" />
    <div class="type">Type: {{ snack.type }}</div>
    <div class="price">Price: ${{ snack.price }}</div>
    <button @click="addToCart(snack)" class="add-to-cart">Add to Cart</button>
  </div>
</template>

<script setup>
import { snacks } from "@/stores/array.js";
import { store } from "@/components/store.js";

function addToCart(snack) {
  store.cart.push({
    name: snack.name,
    price: snack.price,
    img: snack.image,
  });
}
</script>

<style scoped>
.card {
  border: 1px solid #d8d6d6;
  border-radius: 8px;
  margin: 10px;
  padding: 15px;
  text-align: center;
}

.snack-image {
  width: 100%;
  height: 200px;
  object-fit: contain;
}

.name {
  font-size: 2rem;
  margin: 10px;
}

.type,
.price {
  margin-top: 5px;
  font-size: 1.5rem;
}

.add-to-cart {
  margin-top: 10px;
  cursor: pointer;
  background-color: #64a166;
  color: white;
  border: none;
  padding: 10px;
  width: 100%;
  transition: background-color 0.3s ease-in-out;
  font-size: 1.2rem;
}

.add-to-cart:hover {
  background-color: #4e8c5a;
}
</style>
