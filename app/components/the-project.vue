<template>
    <div class="container">
        <div class="title">部分项目展</div>
        <div class="desc">
            以下是近几年的项目，如果有兴趣的话，可以用你发财的<img class="gif" src="/images/click.gif" alt="鼠标点击下面的链接">进去看看。
        </div>
        <!-- <div class="classification">
            <ul>
                <li class="li-active">全部</li>
                <li>网站 & 网页</li>
                <li>后端服务</li>
                <li>游戏</li>
                <li>小程序</li>
            </ul>
        </div> -->
        <div class="projects">
            <ProjectCard v-for="i in datas" :id="i" :key="i" />
        </div>
    </div>
</template>

<script setup lang="ts">
const datas = ["1", "2", "3", "4", "5"];
</script>

<style scoped lang="scss">
@use "@/assets/global.scss" as *;

.container {
    width: 100%;
    padding: 4em clamp(12px, 4em, 32px);
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;

    .title {
        font-size: clamp(18px, 2.2em, 64px);
        font-weight: 600;
        position: relative;
        display: inline-block;
        z-index: 1;

        &::after {
            content: "";
            position: absolute;
            top: 90%;
            left: 0;
            width: 100%;
            z-index: -1;
            height: .1em;
            border-radius: 8px;
            background-color: $theme-color;
        }
    }

    .desc {
        text-align: center;
        padding: 1.5em clamp(12px, 10em, 32px);

        .gif {
            width: clamp(22px, 24em, 28px);
            aspect-ratio: 1/1;
            transform: translateY(25%);
        }
    }

    .classification {
        display: flex;
        justify-content: center;
        align-items: center;
        padding-top: clamp(18px, 1.6em, 32px);

        ul {
            list-style: none;
            user-select: none;
            display: flex;
            flex-wrap: wrap;
            gap: 1em;

            li {
                cursor: pointer;
                padding: 0.6em 1.2em;
                border-radius: 8px;
                background-color: #f8f8f8;
                color: #000;
                font-weight: 600;
            }

            li:hover {
                background: $theme-color;
                color: #fff;
            }

            .li-active {
                background: $theme-color;
                color: #fff;
            }
        }
    }

    .projects {
        width: 100%;
        display: flex;
        justify-content: space-between;
        gap: clamp(12px, 2em, 32px);
        overflow-x: auto;
    }
}
</style>