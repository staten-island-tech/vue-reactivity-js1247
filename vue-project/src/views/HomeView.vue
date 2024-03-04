<template>
  <div>
    <h1 class="welcome">Welcome to the Snack Shop!</h1>
    <SnackCard />
    <router-link to="/checkout" class="checkout-btn">Go to Checkout</router-link>
  </div>
</template>

<script>
import SnackCard from "@/components/SnackCard.vue";

export default {
  components: {
    SnackCard,
  },
};
</script>

<style scoped>
.checkout-btn {
  margin-top: 20px;
  display: inline-block;
  padding: 10px;
  background-color: #64a166;
  color: white;
  text-decoration: none;
  font-size: 1.5rem;
  transition: background-color 0.3s ease-in-out;
}

.checkout-btn:hover {
  background-color: #4e8c5a;
}

.welcome{
  text-align: center;
}
</style>
