<template>
  <div class="card">
    <SnackCard
      v-for="snack in snacks"
      :name="snack.name"
      :type="snack.type"
      :price="snack.price"
      :image="snack.image"
    ></SnackCard>
  </div>
</template>

<script setup>
import { snacks } from "@/stores/array.js";
import SnackCard from "@/components/SnackCard.vue"
</script>

<style scoped>
.card {
  flex-direction: row;
  justify-content: space-evenly;
  display: flex;
  flex-wrap: wrap;
}
</style>
