<template>
  <div>
    <h1 v-if="test">Good</h1>
    <h1 v-else>bad</h1>
    <h2></h2>
  </div>
</template>

<script setup>
const animals = ["zebra", "camel", "ape"];
const test =false;
</script>

<style lang="scss" scoped>

</style>