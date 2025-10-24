<template>
    <div class="container">
        <nav class="nav-box">nav</nav>
        <main>
            <div class="hero-box">hero</div>
            <div class="about-box">about</div>
            <div class="services-box">services</div>
            <div class="projects-box">projects</div>
        </main>
        <footer class="footer-box">footer</footer>
    </div>
</template>

<script setup lang='ts'>
</script>

<style scoped lang="scss">
@use '@/assets/global' as *;

.container {
    display: flex;
    flex-direction: column;
    width: 80vw;
    font-size: 2.4em;
    font-weight: 500;

    @media (max-width: 768px) {
        width: 90vw;
    }

    .nav-box {
        display: flex;
        padding: 3em 0;
    }
}
</style>
