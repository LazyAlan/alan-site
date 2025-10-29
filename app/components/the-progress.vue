<template>
    <div class="progress-ring" id="progress-ring">
        <svg :width="w" :height="h" viewBox="0 0 120 120">
            <circle class="background" cx="60" cy="60" :r="radius" :stroke-width="strokeWidth" />
            <circle class="foreground" cx="60" cy="60" :r="radius" :stroke-width="strokeWidth" ref="foreground" />
            <text class="skill-text" x="50%" y="50%" text-anchor="middle" dy=".3em">
                {{ title }}
            </text>
        </svg>
    </div>
</template>

<script setup lang='ts'>

const props = defineProps({
    title: { type: String, default: 'JS' },
    w: { type: Number, default: 80 },
    h: { type: Number, default: 80 },
    percent: { type: Number, default: 75 }, // 0 - 100
    radius: { type: Number, default: 50 },
    strokeWidth: { type: Number, default: 10 }
});

const foreground = ref<SVGCircleElement | null>(null);
const circumference = computed(() => 2 * Math.PI * props.radius);

function update() {
    if (!foreground.value) return;
    const offset = circumference.value * (1 - props.percent / 100);
    // 确保 dasharray 与 dashoffset 都设置为数字字符串
    foreground.value.setAttribute('stroke-dasharray', String(circumference.value));
    foreground.value.setAttribute('stroke-dashoffset', String(offset));
}

onMounted(() => {
    update();
});

// 响应 percent 变化
watch(() => props.percent, () => update());
</script>

<style scoped lang="scss">
.progress-ring {
    position: relative;
    display: inline-block;
}

.background {
    fill: none;
    stroke: #e6e6e6;
}

.foreground {
    fill: none;
    stroke: orange;
    transform: rotate(-90deg);
    transform-origin: 50% 50%;
    transition: stroke-dashoffset 0.5s ease;
}

.skill-text {
    font-size: 24px;
    fill: orange;
    // font-weight: bold;
}
</style>
