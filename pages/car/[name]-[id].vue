<script setup>
const route = useRoute();
useHead({
    title: toTitleCase(route.params.name),
});

definePageMeta({
    layout: 'custom',
});

function toTitleCase(str) {
    return str.charAt(0).toUpperCase() + str.slice(1);
}
</script>

<template>
    <div>
        <CarDetailHero />
        <CarDetailAttributes />
        <CarDetailDescription />
        <CarDetailContact />
    </div>
</template>