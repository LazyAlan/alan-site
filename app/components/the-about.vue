<template>
    <div class="about-container">
        <div class="avatar">
            <div class="avatar-frame">
                <img src="/images/me.jpg" alt="my photo">
            </div>
        </div>
        <div class="intro">
            <p class="title">关于我</p>
            <p class="desc">
                拥有 10<span class="plus">+</span> 年开发经验，持续致力于 Web 开发，于 24 年末解锁游戏开发技能，拥有前端全栈、后端 .net 开发心得，熟悉 Unity 开发 2D
                游戏及上架微信小游戏流程，拥抱
                Vibe
                coding，注重全局思维与代码质量，注重平衡技术深度与业务需求，当下技能掌握情况如下：
            </p>
            <div class="skill">
                <div class="skill-group">
                    <TheProgress :percent="80" title="C#" />
                    <TheProgress :percent="85" />
                    <TheProgress :percent="75" title="TS" />
                </div>
                <div class="skill-group">
                    <TheProgress :percent="80" title="Html" />
                    <TheProgress :percent="70" title="CSS" />
                    <TheProgress :percent="40" title="Vite" />
                    <TheProgress :percent="30" title="Webpack" />
                </div>
                <div class="skill-group">
                    <TheProgress :percent="85" title=".Net" />
                    <TheProgress :percent="80" title="Vue" />
                    <TheProgress :percent="70" title="Uniapp" />
                    <TheProgress :percent="50" title="Unity" />
                    <TheProgress :percent="50" title="Nuxt" />
                    <TheProgress :percent="60" title="jQuery" />
                </div>
            </div>
        </div>
    </div>
</template>

<script setup lang='ts'>
</script>

<style scoped lang="scss">
@use "@/assets/global.scss" as *;

.about-container {
    display: flex;
    justify-content: space-between;
    padding: 3em 0;
    align-items: center;

    .avatar {
        flex: 1;
        display: flex;
        justify-content: center;
        align-items: center;

        .avatar-frame {
            width: 60%;
            aspect-ratio: 1/1;
            border-radius: 50%;
            position: relative;
            padding: 3px;
            z-index: 1;
            overflow: hidden;

            img {
                width: 100%;
                height: 100%;
                border-radius: 50%;
                display: block;
                object-fit: cover;
                transition: .5s;

                &:hover {
                    transform: scale(1.2);
                    transition: .5s;
                }

            }

            &::before {
                content: "";
                position: absolute;
                inset: 0;
                // border-radius: 50%;
                padding: 3px; // 边框宽度
                background: linear-gradient(135deg, #ff0080, #7928ca, #00ffff);
                z-index: -1;
            }
        }
    }

    .intro {
        flex: 2;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        gap: 1em;

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
            line-height: 1.6;

            .plus {
                display: inline-block;
                transform: translateY(-0.1em) translateX(.1em);
            }
        }

        .skill {
            width: 100%;
            padding-top: 1em;
            user-select: none;
            overflow-x: auto;

            .skill-group {
                display: flex;
                gap: 1.4em;
                padding-bottom: 1.2em;
                overflow-x: auto;
            }
        }
    }

    @media (max-width: 768px) {
        flex-direction: column-reverse;
        padding: 1.2em 0;

        .intro,
        .avatar {
            flex: 1;
            width: 100%;
        }

        .avatar {
            margin-top: 2em;
        }
    }
}
</style>