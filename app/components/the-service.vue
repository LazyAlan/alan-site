<template>
  <div class="container">
    <div class="title">我能做的</div>
    <!-- <div class="desc">
            下面列出目前我能做的项目，如果你有相关需求，欢迎联系我！
        </div> -->
    <div class="card-box">
      <TheCard
        v-for="item in cardList"
        :key="item.icon"
        :icon="item.icon"
        :title="item.title"
        :desc="item.desc"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
const cardList = [
  {
    icon: "/images/h5.png",
    title: "网页设计&开发",
    desc: "以现代标准开发和设计，注重用户体验和响应式布局，确保在各种设备上都能良好展示。",
  },
  {
    icon: "/images/net.png",
    title: "后端服务",
    desc: "使用 .NET 技术栈开发高性能、跨平台和可扩展的后端服务，满足各种业务需求。",
  },
  {
    icon: "/images/game.png",
    title: "2D 游戏开发",
    desc: "使用 Unity 引擎开发 2D 游戏，发不到 Windos、MacOS、Android、IOS、Steam、微信小游戏等平台。",
  },
  {
    icon: "/images/applet.png",
    title: "小程序",
    desc: "使用 uni-app 框架开发跨平台小程序，覆盖微信、支付宝等多个主流平台，快速高效交互。",
  },
];
</script>

<style scoped lang="scss">
@use "@/assets/global.scss" as *;

.container {
  width: 100%;
  padding: 4em clamp(12px, 2em, 32px);
  margin: 0 auto;
  // font-size: clamp(12px, 2em, 32px);
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
      height: 0.1em;
      border-radius: 8px;
      background-color: $theme-color;
    }
  }

  .desc {
    text-align: center;
    padding: 1.5em clamp(12px, 10em, 32px);
  }

  .card-box {
    display: flex;
    justify-content: center;
    padding-top: clamp(24px, 2em, 32px);
    gap: clamp(12px, 2em, 32px);
    flex-wrap: wrap;
  }
}
</style>
