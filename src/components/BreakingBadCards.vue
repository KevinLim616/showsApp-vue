<script setup>
import axios from "axios";

const response = await axios.get("https://www.breakingbadapi.com/api");
</script>
<template>
  <div>
    <h1>{{ response }}</h1>
  </div>
</template>
