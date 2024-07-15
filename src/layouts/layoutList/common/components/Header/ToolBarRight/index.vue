<template>
  <div class="tool-bar-ri">
    <div class="header-icon">
      <SearchMenu id="searchMenu" />
      <ThemeSetting id="themeSetting" />
      <Message id="message" />
      <Fullscreen id="fullscreen" />
    </div>
    <span class="username">{{ username }}</span>
    <Avatar />
  </div>
</template>

<script setup lang="ts">
import { computed } from "vue";

import SearchMenu from "./components/SearchMenu/index.vue";
import ThemeSetting from "./components/ThemeSetting/index.vue";
import Message from "./components/Message/index.vue";
import Fullscreen from "./components/Fullscreen/index.vue";
import Avatar from "./components/Avatar/index.vue";

import { useUserStore } from "@/stores/modules/user";

const userStore = useUserStore();
const username = computed(() => userStore.userInfo.name);
</script>

<style scoped lang="scss">
.tool-bar-ri {
  display: flex;
  justify-content: center;
  align-items: center;
  padding-right: 25px;

  .header-icon {
    display: flex;
    align-items: center;

    & > * {
      margin-left: 21px;
      color: var(--el-header-text-color);
    }
  }

  .username {
    margin: 0 20px;
    color: var(--el-header-text-color);
    font-size: 15px;
  }
}
</style>
