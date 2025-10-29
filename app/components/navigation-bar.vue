<template>
    <nav class="navigation-bar">
        <div class="logo">Alan's shabby little website</div>
        <!-- <div class="nav">
            <ul class="nav-ul">
                <li>首页</li>
                <li>关于</li>
                <li>服务</li>
                <li>联系我</li>
            </ul>
            <div class="hamburger-nav" @click="hamburgerClick">
                <div :class="[hamburgerIsShow ? 'hamburger-close' : 'hamburger-bar']">
                    <div class="hamburger-line">&nbsp;</div>
                    <div class="hamburger-line">&nbsp;</div>
                    <div class="hamburger-line">&nbsp;</div>
                </div>
                <ul v-show="hamburgerIsShow" class="hamburger-ul">
                    <li>首页</li>
                    <li>关于</li>
                    <li>服务</li>
                    <li>联系我</li>
                </ul>
            </div>
        </div> -->
    </nav>
</template>

<!-- <script setup lang='ts'>
const hamburgerIsShow = ref(false);

const hamburgerClick = () => {
    hamburgerIsShow.value = !hamburgerIsShow.value;
};
</script> -->

<style scoped lang="scss">
@use "@/assets/global.scss" as *;

.navigation-bar {
    width: 100%;
    min-width: 30vw;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 2em 0;

    .logo {
        font-size: 2.5em;
        font-family: "ABIMO", sans-serif;
        user-select: none;
    }

    .nav {
        .nav-ul {
            list-style: none;
            display: inline-flex;
            gap: 1em;

            li {
                padding: .5em 1em;
                border-radius: 8px;
                font-weight: 600;
                user-select: none;
                letter-spacing: .1em;
                cursor: pointer;

                &:last-child {
                    background-color: $theme-color;
                }

                &:hover {
                    background-color: $theme-color;
                }
            }
        }

        .hamburger-nav {
            display: none;
            position: relative;
            cursor: pointer;
            user-select: none;

            .hamburger-bar {

                .hamburger-line {
                    width: 1.4em;
                    height: .15em;
                    background-color: $theme-color;

                    &:first-child,
                    &:last-child {
                        width: 70%;
                    }
                }
            }

            .hamburger-close {
                position: relative;
                cursor: pointer;

                .hamburger-line {
                    width: 1.4em;
                    height: .15em;
                    background-color: $theme-color;

                    &:first-child {
                        width: 100%;
                        transform: rotate(45deg);
                    }

                    &:last-child {
                        visibility: hidden;
                    }

                    &:nth-child(2) {
                        width: 100%;
                        transform: rotate(-45deg) translate(.1em, -.1em);
                    }
                }
            }

            .hamburger-ul {
                list-style: none;
                position: absolute;
                background-color: #3e3e3e;
                border-radius: 8px;
                left: -5.8em;
                top: 1.2em;

                li {
                    min-width: 8em;
                    text-align: center;
                    padding: .6em .8em;
                    font-weight: 600;
                    cursor: pointer;

                    &:first-child {
                        border-top-left-radius: 8px;
                        border-top-right-radius: 8px;
                    }

                    &:last-child {
                        background-color: $theme-color;
                        border-bottom-left-radius: 8px;
                        border-bottom-right-radius: 8px;
                    }

                    &:hover {
                        background-color: $theme-color;
                    }
                }
            }
        }

        @media (max-width: 768px) {
            .nav-ul {
                display: none;
            }

            .hamburger-nav {
                display: block;

                .hamburger-bar {
                    display: flex;
                    align-items: center;
                    flex-direction: column;
                    gap: .2em;
                }
            }
        }
    }
}
</style>