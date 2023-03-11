<script setup>
const route = useRoute();
const { toTitleCase } = useUtilities();

useHead({
  title: `${route.params.make ? toTitleCase(route.params.male) : 'Cars'
    } in ${toTitleCase(route.params.city)}`,
});

// layout/custom.vue
definePageMeta({
  layout: 'custom',
});
</script>

<template>
  <div>
    <div class="mt-32 flex">
      <CarSideBar />
      <NuxtPage />
    </div>
  </div>
</template>