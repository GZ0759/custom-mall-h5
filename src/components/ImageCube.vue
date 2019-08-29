<!-- 图片魔方 -->
<template>
  <div class="cube-wrap">
    <div class="cube-title" v-if="cubeData.title">{{ cubeData.title }}</div>
    <div class="cube-img-group" :style="{ height: cubeData.height + 'px' }">
      <CubeMode
        :modeLayout="cubeData.layout"
        :modeSpacing="cubeData.spacing"
        :modeContent="cubeData.images"
      ></CubeMode>
    </div>
  </div>
</template>

<script>
import CubeMode from "@/components/imageCube/CubeMode.vue";
export default {
  components: {
    CubeMode
  },
  props: {
    cubeData: {}
  }
};
</script>

<style>
</style>