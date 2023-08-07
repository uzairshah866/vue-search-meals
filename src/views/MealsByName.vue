<template>
  <div class="p-8">
    <input
      type="text"
      v-model="keyword"
      placeholder="Search for Meals"
      class="rounded border-2 border-gray-200 w-full"
      @change="searchMeals"
    />
  </div>
</template>

<script setup>
const keyword = ref("");

function searchMeals() {}
</script>
