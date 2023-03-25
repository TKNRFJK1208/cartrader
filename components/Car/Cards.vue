<script setup>
const { cars } = useCars();

const favorite = useLocalStorage("favorite", {});

const handleFavorite = (id) => {
  if (id in favorite.value) {
    delete favorite.value[id]
  } else {
    favorite.value = {
      ...favorite.value,
      [id]: true
    }
  }
}
</script>

<template>
  <div>
    <!-- in order to load only client side -->
    <CarCard v-for="car in cars" :key="car.id" :car="car" @favorite="handleFavorite" :favorite="car.id in favorite" />
  </div>
</template>