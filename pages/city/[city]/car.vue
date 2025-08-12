<script setup>
const route = useRoute();
useHead({
    title: `${route.params.make ? toTitleCase(route.params.make) : 'Car'} - in ${toTitleCase(route.params.city)}`,
});

definePageMeta({
    layout: 'custom',
});

function toTitleCase(str) {
    return str.charAt(0).toUpperCase() + str.slice(1);
}
</script>

<template>
    <div class="mt-32 flex">
        <CarSideBar />
        <NuxtPage />
    </div>
</template>