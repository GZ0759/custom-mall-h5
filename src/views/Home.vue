<template>
  <div class="home">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <ImageCube :cubeData="value" v-for="(value, key, index) in cubes" :key="index" />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import ImageCube from "@/components/ImageCube.vue";

export default {
  name: "home",
  components: {
    ImageCube
  },
  props: {
    cubeData: {}
  },
  data() {
    return {
      cubes: {}
    };
  },
  methods: {
    getCubeData() {
      let that = this;
      this.$axios
        .get("/mock.json")
        .then(function(res) {
          if (res.status === 200) {
            that.cubes = res.data.cubes;
          }
        })
        .catch(function(error) {
          console.log(error);
        });
    }
  },
  mounted() {
    this.getCubeData();
  }
};
</script>
