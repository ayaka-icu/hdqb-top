<script setup>
import {copyToClipboard} from "@/utils/CopyUtils.js";
</script>

<template>
  <div>
    <a-divider :margin="10" style="margin: 25px 0">
      <div style="background-color: #C5C1FF;padding: 3px 8px;border-radius: 5px;">
        新章
        <icon-star/>
        - 起点
      </div>
    </a-divider>
    <a-alert :show-icon="false">&emsp;&emsp;一个起点，也意味着上一个故事的序幕。如今，这天的到来，本以为会轻松很多，可当工作和生活的压力，曾使我一度放弃......但你们的鼓励，让我看见了一束光芒，是让我继续书写的动力......
    </a-alert>
    <a-divider :margin="10" style="margin: 25px 0">
      <div style="background-color: #4facfe;padding: 3px 8px;border-radius: 5px;">
        新章
        <icon-star/>
        - 仰望
      </div>
    </a-divider>
    <a-alert :show-icon="false">&emsp;&emsp;仰望前方，又是一片新天地，探索是人类的本性，不应安于此！<br>
      &emsp;&emsp;我有意愿<span style="font-weight: bold;color: red">为海岛🏝开发一个手机APP</span>，一方面是学习Flutter跨平台开发，一方面是为海岛🏝为大家做点什么~
      <span style="color: red">不过，我不知道能否完成，因为我是一个追求完美的人，项目也可能半路夭折，我尽力吧~</span><br>
      &emsp;&emsp;如果你有什么好的意见或者加入这个项目，请联系QQ群：
      <a-link @click="copyToClipboard('555080859')">555080859</a-link>
    </a-alert>
    <a-divider :margin="10" style="margin: 25px 0">
      <div style="background-color: aquamarine;padding: 3px 8px;border-radius: 5px;">
        新章
        <icon-star/>
        - 启航
      </div>
    </a-divider>
    <a-alert :show-icon="false">&emsp;&emsp;有了希望，有了方向，有了官方的态度，有了你们，让我们携手共进，一起杨帆，启航！🌊🌊🌊⚡🌊🌊🌊🌊🌊❄️🌊🌊🌊🌊🌊☂️🌊🌊🌊🌊⛈️🌊🌊🌊🌊🌊☔🌊🌊🌊🌈⛵🏝
    </a-alert>
  </div>
</template>
<style lang="scss" scoped>
</style>