<template>
  <div>
    <h1>Checkout</h1>
    
    <div v-if="cart.length === 0">Your cart is empty</div>
    <div v-else>
      <ul>
        <li v-for="(item, index) in cart" :key="index">
          {{ item.name }} - ${{ item.price }}
        </li>
      </ul>
      <div>Total: ${{ calculateTotalPrice() }}</div>
      <button @click="completePurchase" class="complete-purchase">Complete Purchase</button>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import { store } from "@/components/store.js";

const cart = ref(store.cart);

function calculateTotalPrice() {
  return cart.value.reduce((total, item) => total + item.price, 0);
}

function completePurchase() {
  console.log('Purchase completed!');
}
</script>

<style scoped>
.complete-purchase {
  margin-top: 10px;
  cursor: pointer;
  background-color: #64a166;
  color: white;
  border: none;
  padding: 10px;
  width: 100%;
  transition: background-color 0.3s ease-in-out;
  font-size: 2rem;
}

.complete-purchase:hover {
  background-color: #4e8c5a;
}
</style>
