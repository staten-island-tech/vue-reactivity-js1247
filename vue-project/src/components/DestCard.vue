<template>
  <div>
    <h1>{{ Destination.name }}</h1>
  </div>
</template>

<script setup>
const props = defineProps({
  Destination: Object,
});
</script>

<style lang="scss" scoped></style>
