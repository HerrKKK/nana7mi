<template>
    <el-menu
        :default-active="1"
        class="el-menu-demo"
        mode="horizontal"
        menu-trigger="click"
        unique-opened
    >
      <el-sub-menu index="1">
        <template #title>相关链接</template>
        <el-menu-item index="1-1" @click="clickHandle($event)">VirtuaReal</el-menu-item>
        <el-menu-item index="1-2" @click="clickHandle($event)">Nana7mi-直播间</el-menu-item>
        <el-menu-item index="1-3" @click="clickHandle($event)">Nana7mi-个人主页</el-menu-item>
        <el-menu-item index="1-4" @click="clickHandle($event)">Nana7mi-萌娘百科</el-menu-item>
      </el-sub-menu>
      <el-popover placement="bottom" :width="500" trigger="click">
        <template #reference>
          <el-button>版权说明</el-button>
        </template>
          <el-descriptions column=2 >
            <el-descriptions-item label-align="right" align="left" label="作者">
              <a href="https://space.bilibili.com/20769654" target="_blank">打牙专家&nbsp;&nbsp;</a>
              <a href="https://space.bilibili.com/228042796" target="_blank">彩彩Aya</a>
            </el-descriptions-item>
            <el-descriptions-item label-align="right" align="left" label="图片版权">
              <a href="https://space.bilibili.com/1883330" target="_blank">再也不吃柠檬炸鸡&nbsp;&nbsp;</a>
              <a href="https://space.bilibili.com/1999511110" target="_blank">kachiyu_</a>
            </el-descriptions-item>
            <el-descriptions-item label-align="right" align="left" label="开源软件">
              <a href="https://github.com/vuejs/vue" target="_blank">Vue.js&nbsp;&nbsp;&nbsp;</a>
              <a href="https://github.com/element-plus/element-plus" target="_blank">Element-plus &nbsp;&nbsp;</a>
              <a href="https://jquery.com/" target="_blank">jQuery &nbsp;&nbsp;</a>
              <a href="https://getbootstrap.com/" target="_blank">Bootstrap.grid</a>
            </el-descriptions-item>
          </el-descriptions>
      </el-popover>
      <el-popover
          placement="bottom"
          :width="250"
          trigger="click"
      >
        <template #reference>
          <el-button>关于本站</el-button>
        </template>
        <el-descriptions column=1>
          <el-descriptions-item label-align="right" align="left" label="本站是VirtuaReal旗下虚拟主播七海Nana7mi的非官方网站"></el-descriptions-item>
          <el-descriptions-item label-align="right" align="left" label="项目地址">
            <a href="https://github.com/HerrKKK/nana7mi" target="_blank">Github</a>
          </el-descriptions-item>
          <el-descriptions-item label-align="right" align="left" label="如对本站有任何意见或建议"></el-descriptions-item>
          <el-descriptions-item label-align="right" align="left" label="请联系">
            <a href="mailto:ybb@nana7mi.com">ybb@nana7mi.com</a>
          </el-descriptions-item>
        </el-descriptions>
      </el-popover>
    </el-menu>
</template>

<script>
import { defineComponent, ref } from 'vue'

export default defineComponent({
  setup() {
    const activeIndex = ref('0');
    const linkList = {
      '1-1': 'https://vrp.live/member/nanami',
      '1-2': 'https://live.bilibili.com/21452505',
      '1-3': 'https://space.bilibili.com/434334701',
      '1-4': 'https://zh.moegirl.org.cn/七海(虚拟UP主)'
    };
    const handleSelect = (key, keyPath) => {
      console.log(key, keyPath);
    };
    const clickHandle = (e) => {
      // console.log(e.index);
      window.open(linkList[e.index], "_blank");
    };
    return {
      activeIndex,
      handleSelect,
      clickHandle,
    }
  },
})
</script>
<style scoped>
button {
  border: none;
  color: black;
}
</style>
