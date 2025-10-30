<template>
    <div class="card-container">
        <div class="icon">
            <img :src="icon" alt="icon">
        </div>
        <div class="title">
            {{ title }}
        </div>
        <div class="desc">
            {{ desc }}
        </div>
    </div>
</template>

<script setup lang='ts'>
const props = defineProps({
    icon: { type: String, required: true },
    title: { type: String, required: true },
    desc: { type: String, required: true },
})
console.log(props);
</script>

<style scoped lang="scss">
@use "@/assets/global.scss" as *;

.card-container {
    width: clamp(200px, 80vw, 300px);
    height: auto;
    background-color: #fff;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    color: #000;
    padding: clamp(10px, 2em, 16px) clamp(10px, 1.2em, 24px);
    border-radius: 8px;

    .icon {
        width: clamp(2em, 4em, 6em);
        aspect-ratio: 1/1;

        img {
            width: 100%;
            height: 100%;
            display: block;
        }
    }

    .title {
        padding: clamp(4px, .5em, 10px) 0;
        font-weight: 600;
        font-size: $font-size-normal;
    }

    .desc {
        line-height: 1.6;
    }
}
</style>