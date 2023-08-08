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
import { computed } from "vue";
import store from "../store";

const keyword = ref("");

const meals = computed(() => store.state.searchedMeals);

function searchMeals() {
  store.dispatch("searchMeals", keyword.value);
}
</script>
