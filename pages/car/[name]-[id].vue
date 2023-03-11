<script setup>
const route = useRoute();
const { toTitleCase } = useUtilities();

useHead({
  title: toTitleCase(route.params.name),
})

// layout/custom.vue
definePageMeta({
  layout: 'custom',
});

</script>

<template>
  <div>
    <CarDetailHero />
    <CarDetailAttributes />
    <CarDetailDescription />
    <CarDetailContact />
  </div>
</template>