<template>
    <div class="the-hero">
        <div class="intro">
            <p class="hi">嗨，我是 <span class="name">Alan Xu</span></p>
            <p class="skilled">Web & 游戏 开发者</p>
            <p class="intro-text">深耕 Web 与游戏开发的数字游民（心态），始终以简单、优雅实现为目标，在全栈开发与引擎应用中持续精进。既熟练驾驭前后端框架，也能在 Unity
                引擎中打磨游戏渲染与玩法逻辑，用高效代码实现流畅体验与视觉呈现的平衡。我坚信终身学习是技术人的核心竞争力，始终保持学徒心态，积极探索新技术，力求在每个项目中交付卓越成果。</p>
        </div>
        <div class="avatar">
            <div class="avatar-frame">
                <img src="/images/son.png" alt="my lovely child" />
            </div>
        </div>
    </div>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
@use "@/assets/global.scss" as *;

.the-hero {
    display: flex;
    justify-content: space-between;
    padding: 3em 0;
    align-items: center;

    .intro {
        flex: 2;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        gap: 1em;

        .name {
            padding: 0 .2em;
            color: $theme-color;
            font-size: clamp(24px, 1.8em, 64px);
        }

        .skilled {
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

        .intro-text {
            line-height: 1.6;
        }
    }

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
                content: '';
                position: absolute;
                inset: 0;
                border-radius: 50%;
                padding: 3px; // 边框宽度
                background: linear-gradient(135deg, #ff0080, #7928ca, #00ffff);
                z-index: -1;
            }

            .avatar-intro {
                font-size: clamp(10px, .8em, 1em);
                width: 100%;
                position: absolute;
                top: 90%;
                left: 35%;
            }
        }
    }

    @media (max-width: 768px) {
        flex-direction: column;

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
