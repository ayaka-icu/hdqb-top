<script setup>

import {ref} from "vue";
import {BannedList} from "@/data/BannedList.js";
import {copyToClipboard} from "@/utils/CopyUtils.js";

const bannedList = ref(BannedList)
</script>

<template>
  <div>
    <div style="width: 100%;display: flex;justify-content: center">
      <img src="https://ayaka-icu-oss.oss-cn-beijing.aliyuncs.com/hdqb/web/hdgg01.png" class="gg-img"
           alt="海岛奇兵官方公告">
    </div>
    <!--  玩家列表  -->
    <div style="width: 100%;display: flex;justify-content: center">
      <a-list class="gg-img">
        <template #header>
          <div style="width: 100%;height: 30px;">
            也许审判会迟到，但绝不会缺席！
          </div>
        </template>
        <a-list-item v-for="(item, index) in bannedList" :key="index">
          <div class="item-left">
            {{ index + 1 }}. {{ item }}
          </div>
        </a-list-item>
        <a-list-item>
          <div style="float: right">
            QQ群:
            <a-link @click="copyToClipboard('555080859')">555080859</a-link>
          </div>
        </a-list-item>
      </a-list>
    </div>
  </div>
</template>

<style scoped>
.gg-img {
  width: 100%;
  opacity: 0.8;
}

/* PC 端样式 */
@media screen and (min-width: 769px) {
  .gg-img {
    width: 70vh;
  }
}

.item-left-title {
  display: flex;
  justify-content: flex-start;
  align-items: center;
}

.item-left {
  font-size: 14px;
  font-weight: bold;
  justify-content: flex-start;
  display: flex;
  align-items: center;
}

.item-right {
  flex: 1;
  justify-content: flex-end;
  display: flex;
  align-items: center;
}

:deep(.arco-list-medium .arco-list-content-wrapper .arco-list-header) {
  padding: 12px 20px;
  background-image: linear-gradient(to right, #4facfe 0%, #00f2fe 100%);
}
</style>