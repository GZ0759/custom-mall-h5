<template>
  <div class="mode-wrap">
    <CubeUnit
      :cubeContentItem="item"
      v-for="(item, index) in modeContent"
      :key="index"
      class="mode-item"
    />
  </div>
</template>

<script>
import CubeUnit from "@/components/imageCube/CubeUnit.vue";
export default {
  components: {
    CubeUnit
  },
  props: {
    modeLayout: "", // 布局名称
    modeSpacing: false, // 间隔线
    modeContent: {} // 最小魔方单位内容
  }
};
</script>

<style lang="scss" scoped>
.mode-wrap {
  width: 100%;
  height: 100%;
  display: flex;
  >>> div {
    height: 100%;
  }
  .mode-item {
    flex: 1;
  }
}
</style>