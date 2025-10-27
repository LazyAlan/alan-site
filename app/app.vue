<template>
  <div class="app-container">
    <NuxtRouteAnnouncer />
    <div class="app-box">
      <NavigationBar />
      <NuxtPage />
    </div>
  </div>
</template>

<script setup lang="ts">
useSeoMeta({
  title: "Alan's site",
  description: "This is my personal site",
})
</script>

<style scoped lang="scss">
.app-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 80vw;
  margin: 0 auto;

  @media (max-width: 768px) {
    width: 90vw;
  }

  .app-box {
    width: 100%;
  }
}
</style>