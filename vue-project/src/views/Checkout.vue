<template>
  <div class="checkout">
    <h1>Checkout</h1>

    <div v-if="cart.length === 0">
      <h2>Your cart is empty</h2>
    </div>
    <div v-else>
      <div v-for="(item) in cart" class="cart-item">
        <h2>{{ item.name }} - ${{ item.price }}</h2>
      </div>
      <div class="total-price">
        <h2>Total: ${{ calculateTotalPrice() }}</h2>
      </div>

      <button @click="completePurchase" class="complete-purchase">Complete Purchase</button>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import { store } from "@/components/store.js";

const cart = ref(store.cart);

function calculateTotalPrice() {
  return cart.value.reduce((total, item) => total + Number(item.price), 0);
}

function completePurchase() {
  window.alert('Thank you for shopping!');
  store.cart = [];
}
</script>

<style scoped>
.checkout {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
}

h1 {
  font-size: 2.5rem;
  margin-bottom: 20px;
}

h2 {
  font-size: 1.8rem;
  color: grey;
}

.cart-item {
  border-bottom: 1px solid #ddd2d2;
  padding: 10px;
  align-items: center;
}

.total-price {
  margin-top: 15px;
  font-size: 1.2rem;
}

.complete-purchase {
  margin-top: 20px;
  cursor: pointer;
  background-color: #64a166;
  color: white;
  border: none;
  padding: 15px;
  width: 100%;
  transition: background-color 0.3s ease-in-out;
  font-size: 1.5rem;
}

.complete-purchase:hover {
  background-color: #4e8c5a;
}
</style>


