<script setup>
import BreakingBadCards from "./components/BreakingBadCards.vue";
</script>

<template>
  <main>
    <h1>HERO</h1>
    <Suspense>
      <BreakingBadCards />

      <template #fallback>
        <div>
          <p>loading...</p>
        </div>
      </template>
    </Suspense>
  </main>
</template>

<style scoped></style>
