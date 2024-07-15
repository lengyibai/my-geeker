<template>
  <div class="tool-bar-lf">
    <Collapse />
    <Breadcrumb v-show="globalStore.breadcrumb" />
  </div>
</template>

<script setup lang="ts">
import Collapse from "./components/Collapse/index.vue";
import Breadcrumb from "./components/Breadcrumb/index.vue";

import { useGlobalStore } from "@/stores/modules/global";
const globalStore = useGlobalStore();
</script>

<style scoped lang="scss">
.tool-bar-lf {
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  white-space: nowrap;
}
</style>
