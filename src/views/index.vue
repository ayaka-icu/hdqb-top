<template>
  <div>
    <Particles id="tsparticles" :options="options" v-if="isSakuraBg"/>

    <div style="min-height: 900px;position: relative;padding: 0 10px;margin-bottom: 100px">
      <!--  头部 TODO: 加个背景图吧以后！ -->
      <a-alert type="success" closable class="alert-top" :show-icon="false">
        <span style="color: #def416">这里是 《海岛奇兵》hdqb.icu 🐕🏥</span>
      </a-alert>
      <!--  导航  -->
      <PageHead @change-type="changeType" ref="pageHeadRef"/>
      <!--  卡狗榜  -->
      <NoticePage v-show="type === 1"/>
      <!--  绿玩榜  -->
      <NewChapterPage v-show="type === 2"/>
      <!--  官网  -->
      <HistoryPage @goKagouList="goType(1)" v-show="type === 3"/>
      <ChatPage v-show="type === 4"/>

      <a-modal v-model:visible="infoModal" @before-open="setWidth()" unmountOnClose width="90vw"
               body-style="padding: 8px">
        <template #title>
          致谢！
        </template>
        <a-alert :show-icon="false" style="margin-bottom: 8px">&emsp;&emsp;亲爱的『岛友们🏝』，💕感谢你们的陪伴~
          你们的努力，是我坚持的动力！这是所有坚持公平、绿色游戏的指挥官们一起努力的结果，每个人都是至死不渝的传奇🌟！
        </a-alert>
        <a-alert type="success" :show-icon="false" style="margin-bottom: 8px">&emsp;&emsp;亲爱的『海岛奇兵官方』，💕感谢你们耐心聆听玩家的反馈，对公平绿色游戏环境做出的努力。审判也许会迟到，但从不缺席！</a-alert>
        <a-alert type="warning" :show-icon="false">
          <div>
            &emsp;&emsp;黎明已至，新的曙光已经到来！让我们共同努力，愿海岛🏝长存~
          </div>
          <div style="float: right">
            <icon-schedule/>
            2025-04-01
          </div>
        </a-alert>
        <template #footer>
          <a-button type="primary" @click="infoModal = false">让我们一起加油吧！</a-button>
        </template>
      </a-modal>

    </div>

    <FloatingSettingButton @sakura-bg="sakuraBg"/>
  </div>

</template>
<script setup>
import {h, ref} from "vue"
import PageHead from "@/layout/PageHead.vue";
import NoticePage from "@/views/NoticePage.vue";
import NewChapterPage from "@/views/NewChapterPage.vue";
import HistoryPage from "@/views/HistoryPage.vue";
import ChatPage from "@/views/ChatPage.vue";
import FloatingSettingButton from "@/components/FloatingSettingButton.vue";
import {Message} from "@arco-design/web-vue";
import {IconCommand} from '@arco-design/web-vue/es/icon';
import Sakura1 from "@/assets/sakura1.svg";
import Sakura2 from "@/assets/sakura2.svg";
import Sakura3 from "@/assets/sakura3.svg";

const pageHeadRef = ref();

const type = ref(1);

const isSakuraBg = ref(true);

const infoModal = ref(true);

const changeType = (newType) => {
  type.value = newType;
}

const goType = (newType) => {
  pageHeadRef.value.changeType(newType);
}

const sakuraBg = () => {
  isSakuraBg.value = !isSakuraBg.value;
}
Message.success({
  content: '黎明已至，新的曙光已经到来！',
  icon: () => h(IconCommand),
  duration: 3800,
  closable: true
})

//配置particles
const options = {
  fullScreen: {
    enable: true,
    zIndex: -1
  },
  particles: {
    number: {
      value: 110,
      density: {
        enable: true,
        value_area: 800
      }
    },
    color: {
      value: "#ffc0cb"
    },
    /*shape: {
      type: "char",
      character: {
        value: ["🌸"],
      }
    },*/
    shape: {
      type: "image", // 修改为 'image' 以使用图片
      image: [
        {
          src: Sakura1,
          width: 21,
          height: 21
        },
        {
          src: Sakura2,
          width: 22,
          height: 22
        },
        {
          src: Sakura3,
          width: 20,
          height: 20
        }
        // 可按需添加更多 SVG 图片配置
      ]
    },
    opacity: {
      value: 0.8,
      random: false,
      anim: {
        enable: false
      }
    },
    size: {
      value: 16,
      random: true,
      anim: {
        enable: false
      }
    },
    line_linked: {
      enable: false
    },
    move: {
      enable: true,
      speed: 4,
      direction: "bottom-left",
      random: true,
      straight: true,
      out_mode: "out",
      bounce: false,
      attract: {
        enable: false
      }
    }
  },
  interactivity: {
    events: {
      onhover: {
        enable: false
      },
      onclick: {
        enable: false
      }
    }
  },
  retina_detect: true
};
</script>
<style scoped>
.alert-top {
  margin-top: 5px;
  background-image: url('https://ayaka-icu-oss.oss-cn-beijing.aliyuncs.com/hdqb/web/card-bg.png');
  background-size: 100% auto; /* 宽度自动调整以保持比例，高度设置为容器高度的100% */
  background-position: right center; /* 背景图片右对齐且垂直居中 */
  background-repeat: no-repeat;
  display: flex;
  font-size: 20px;
  font-weight: bold;
  min-height: 120px;
}

/* 手机 alert-top*/
@media screen and (max-width: 768px) {
  .alert-top {
    min-height: 60px;
    font-size: 16px;
  }
}
</style>