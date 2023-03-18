<script setup>
const { cars } = useCars();
</script>

<template>
  <div>
    <CarCard v-for="car in cars" :key="car.id" :car="car" />
  </div>
</template>