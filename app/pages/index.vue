<template>
    <div class="container">
        <main>
            <TheHero />
            <TheAbout />
            <TheService />
            <TheProject />
        </main>
        <footer class="footer">
            <!-- <div class="slogan">世事总是无常 来日并不方长</div> -->
        </footer>
    </div>
</template>

<script setup lang='ts'>

</script>

<style scoped lang="scss">
.container {
    display: flex;
    flex-direction: column;

    .footer {
        height: 100px;
    }
}
</style>
