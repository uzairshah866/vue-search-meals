<template>
  <div class="flex flex-col p-8">
    <div>
      <input
        type="text"
        placeholder="Search for Meals"
        class="rounded border-2 border-gray-200 w-full"
      />
    </div>
    <div class="flex justify-center gap-2 mt-2">
      <router-link
        :to="{ name: 'byLetter', params: { letter } }"
        v-for="letter of letters"
        :key="letter"
      >
        {{ letter }}
      </router-link>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import axiosClient from "../axiosClient.js";

const letters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ".split("");
const ingredients = ref([]);

onMounted(async () => {
  const response = await axiosClient.get("list.php?i=list");
  console.log({ response });
  ingredients.value = response.data;
});
</script>
