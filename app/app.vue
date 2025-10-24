<template>
  <div class="app-container">
    <NuxtRouteAnnouncer />
    <div class="nav-box">
      <NavigationBar />
    </div>
    <NuxtPage />
  </div>
</template>

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

  .nav-box {
    width: 100%;
  }
}
</style>