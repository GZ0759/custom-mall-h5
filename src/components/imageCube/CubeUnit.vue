<template>
  <div class="unit-wrap">
    <div v-if="cubeContentItem.type === 'video'">
      <!-- 视频 -->
      <video :src="cubeContentItem.video"></video>
    </div>
    <div v-else>
      <!-- 图片 -->
      <van-image
        :src="cubeContentItem.image"
        fit="fill"
        @click="unitClick(cubeContentItem.src || '')"
      ></van-image>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    cubeContentItem: {}
  },
  methods: {
    unitClick(src) {
      console.log("跳转至", src);
    }
  }
};
</script>

<style lang="scss" scoped>
.unit-wrap {
  width: 100%;
  height: 100%;
}
</style>