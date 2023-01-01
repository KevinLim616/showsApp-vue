<script setup>
import axios from "axios";
import { ref, watch } from "vue";

const characters = ref(null);
const page = ref(0);

const response = await axios.get(
  `https://breakingbadapi.com/api/characters?limit=8&offset=8`
);
characters.value = response.data;

//whenever click to the next page it renders another 8 items/characters
watch(page, async () => {
  const response = await axios.get(
    `https://breakingbadapi.com/api/characters?limit=8&offset=${page.value * 8}`
  );
  characters.value = response.data;
});
</script>
<template>
  <div>
    <h1>{{ characters }}</h1>
    <div>
      <button @click="page++">Next</button>
      <button @click="page--">Back</button>
    </div>
  </div>
</template>
