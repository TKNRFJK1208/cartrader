<script setup>
const city = ref('');
const cityError = ref(false);

const handleSearch = () => {
  // Handle search logic here, e.g., emit an event or navigate to a search results page
  console.log(`Searching for cars in ${city.value}`);
  if(!city.value) {
    return cityError.value = true;
  }
  navigateTo(`/city/${city.value}/car`);
};
</script>

<template>
    <div
          class="font-serif w-[1000px] text-2xl rounded-full bg-white flex justify-between overflow-hidden drop-shadow-2xl mx-auto"
        >
          <input
            type="text"
            class="py-3 px-5 w-full text-2xl rounded-full focus:outline-none"
            :class="{'border-red-500': cityError}"
            placeholder="Search by city..."
            v-model="city"
            @keyup.enter="handleSearch"
          />
          <button class="bg-sky-500 px-10 text-white">Search</button>
        </div>
</template>