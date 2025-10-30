<template>
    <div class="container-card" @click="clickHandler">
        <div class="box">
            <img :src="mapData.get(props.id).image" :alt="mapData.get(props.id).title" />
        </div>
        <div class="title">{{ mapData.get(props.id).title }}</div>
    </div>
    <teleport to="body">
        <div v-show="isOpen" class="modal-container">
            <div class="modal">
                <div class="close-icon" @click="closeModal">&times;</div>
                <div class="modal-content">
                    <div class="modal-img">
                        <img :src="mapData.get(props.id).image" :alt="mapData.get(props.id).title" />
                    </div>
                    <div class="model-desc">
                        <div class="modal-title">{{ mapData.get(props.id).title }}</div>
                        <div class="desc">{{ mapData.get(props.id).desc }}</div>
                    </div>
                </div>
            </div>
        </div>
    </teleport>
</template>

<script setup lang="ts">
const props = defineProps({
    id: { type: String, required: true },
});

const isOpen = ref(false);

const clickHandler = () => (isOpen.value = !isOpen.value);

const closeModal = () => (isOpen.value = false);

const mapData = new Map();
mapData.set("1", {
    title: "哈马哈游记",
    image: "/images/projects/hamahayouji.png",
    desc: `哈马哈游记是一个 2D 横版通关游戏，作为我学习 Unity 开发游戏的成果验证只制作了一个关卡，游戏玩法类似于任天堂早期的冒险游戏，玩家跑完地图，并在最终击败关底 Boss 通关。\n
    主角是一只可爱的小猫咪，它可以跑酷，可以跳跃，可以攻击（近战和远程攻击），近战攻击可以积攒能量，能量积满后兑换为一个终极技能，终极技能拥有高伤害，可以造成范围伤害，但最多只能兑换 3 个，释放技能后可以重新累计和兑换。玩家会受到敌人和陷阱的伤害，当健康值清空的时候游戏失败。\n
    游戏里的敌人有各自不同的特点，玩家触碰它们都会受到伤害，第一类敌人会发起远程攻击，他们能感应到玩家靠近，并在靠近到一定距离后发射子弹攻击玩家，第二类是会移动的敌人，当玩家靠近他们时，他们会进入防御状态，如果玩家攻击他们，他们就会追击玩家并发起攻击，第三类敌人躲在地图上，当玩家靠近时快速冲击并攻击玩家，他们不能被玩家攻击，关底 Boss 拥有强大的攻击力，可以轻松击败玩家。\n
    项目使用 Unity 引擎开发，使用 C# 编写脚本，通过插件转换为微信小游戏，游戏美术多为免费资源和 AI 辅助生成。\n
    游戏已上架微信小游戏，可搜索“哈马哈游记”试玩。`
});
mapData.set("2", {
    title: "予哈壁纸",
    image: "/images/projects/yuhawallpaper.png",
    desc: `予哈壁纸是一个微信小程序项目，用户界面使用 uni-app 开发，后端使用 Asp.net WebAPI 提供服务，借助生成式 AI 的爆发，我在本地部署 Stable Diffusion 生成了很多高质量的图片，于是谋生了出一款壁纸小程序的想法。\n
    小程序的主要功能是图片预览、搜索和下载，因为本地算力不足，后期从某壁纸网爬取了很多图，图片爬取程序是自己写的，它主要负责分析网站的 html 结构，结合 XPath 读取图片真实地址，然后记录图片地址，下载程序获取图片地址下载图片，同时生成一个小的预览图，把这两个图片存储到腾讯云的存储桶里，拿到返回的地址存储 mysql 数据库，提供给 webAPI 调用。腾讯云的存储桶用的是半年试用，随着存储桶到期，壁纸小程序也停止了服务。\n
    这个项目虽然小，但是用的东西多，使用的东西大概包括：\r
    C# + Asp.net WebAPI + TypeScript + uni-app + 腾讯云对象存储 + 腾讯云服务器 + CentOS 7 + Nginx`
});
mapData.set("3", {
    title: "健康龙陵",
    image: "/images/projects/ll4.png",
    desc: `健康龙陵是公司的微信公众号项目，使用 Vue2 开发，也是我第一次使用 Vue，是边看文档边实践的成果，健康龙陵提供了县域医共体服务，项目获得了云南省最佳基层应用奖和智慧医疗创新应用二等奖。\n
    项目主要功能包含预约挂号、诊间支付、检验检测报告查询、就诊记录查询、图文会诊、个人中心、就诊人管理、微信电子健康卡等等，为龙陵县提供医共体服务，使用的医院是所有县域内的公立医院，包括龙陵县人民医院、中医院、妇幼保健院和所有乡镇卫生院，这个项目主要包含三个部分，一个用户界面，一个管理后台和一个 WebAPI 服务，我做了所有的用户界面工作和一部分 WebAPI 服务。\n
    项目使用的的东西大概包含：\r
    C# + Asp.net WebAPI + Vue2 + 微信支付 + 微信公众号 + 微信电子健康卡 + Nginx + MySQL + CentOS 7 + VantUI`
});
mapData.set("4", {
    title: "医疗自助机",
    image: "/images/projects/machine.jpeg",
    desc: `这是一个医院里的智能终端设备项目，主要功能是预约挂号、在线建档、自助缴费、单据打印、住院办理等服务。\n
    这个项目只做了用户界面，是使用 Vue3 开发的，没有使用组件库，所有 UI 都是自己实现的，Vue3(JavsScript) 和硬件交互中间使用了一个叫做 CefSharp 的开源框架，CefSharp 内置 chromium 浏览器，CefSharp 暴露接口到 window 对象上供JavaScript 调用，数据交互还是通常的 http 请求。\n
    项目使用的东西大概包含：\r
    Vue3 + CefSharp + Asp.net WebAPI + 硬件交互(厂商提供的 SDK)`
});
mapData.set("5", {
    title: "通用医疗公众号",
    image: "/images/projects/public-web.png",
    desc: `这个项目算是 Vue3 重写的健康龙陵，使用最新的技术栈，重构了后端服务。\n
    项目使用的东西大致包含：\r
    C# + Asp.net WebAPI + Vue3 + 微信支付 + 微信公众号 + 微信电子健康卡 + Nginx + MySQL + CentOS 7 + VantUI`
});
</script>

<style scoped lang="scss">
.container-card {
    padding-top: clamp(16px, 3em, 64px);
    cursor: pointer;
    user-select: none;

    .box {
        width: clamp(280px, 7em, 350px);
        height: clamp(350px, 7em, 400px);
        background-color: #ffebdb;
        border-radius: 8px;

        img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
            border-radius: 8px;
        }
    }

    .title {
        padding: clamp(8px, 1em, 24px) 0;
        font-weight: 600;
        text-align: center;
    }
}

.modal-container {
    width: 100vw;
    height: 100vh;
    background-color: rgb(62, 62, 62, 0.9);
    position: fixed;
    z-index: 999;

    .modal {
        width: clamp(60%, 80%, 100%);
        height: clamp(60%, 80%, 100%);
        background-color: rgb(0, 0, 0);
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        border-radius: 8px;
        padding: 2em;
        display: flex;
        flex-direction: column;

        .close-icon {
            margin-left: auto;
            user-select: none;
            font-size: 2em;
            transition: 0.5s;

            &:hover {
                cursor: pointer;
                transform: scale(1.2);
                transition: 0.5s;
            }
        }

        .modal-content {
            display: flex;
            gap: 1.2em;
            height: 100%;

            .modal-img {
                img {
                    border-radius: 8px;
                    // width: clamp(10em, 300px, 20em);
                    // width: 100%;
                }

                @media (max-width: 768px) {
                    display: none;
                }
            }

            .model-desc {
                height: 100%;
                overflow-y: hidden;

                .modal-title {
                    margin: 0 auto;
                    font-size: 2em;
                    font-weight: 600;
                    margin-bottom: 0.4em;
                }

                .desc {
                    overflow-y: auto;
                    height: 80%;
                    line-height: 1.5;
                    white-space: pre-line;
                }
            }
        }
    }
}
</style>
