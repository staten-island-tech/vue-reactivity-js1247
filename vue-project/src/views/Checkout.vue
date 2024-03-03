<template>
  <div class="checkout-container">
    <h1>Checkout</h1>

    <div v-if="cart.length === 0">
      <h1>Your cart is empty</h1>
    </div>
    <div v-else>
      <div v-for="(item) in cart" class="cart-item">
        <h1>{{ item.name }} - ${{ item.price }}</h1>
      </div>
      <div class="total-price">
        <h1>Total: ${{ calculateTotalPrice() }}</h1>
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
.checkout-container {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
}

.cart-item {
  border-bottom: 1px solid #ebe2e2;
  padding: 15px;
  display: flex;
  justify-content: space-between;
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
