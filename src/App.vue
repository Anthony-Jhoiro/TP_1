<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <!-- <Carousel
    :imageList="[
      'https://picsum.photos/200/300?random=0',
      'https://picsum.photos/200/300?random=1',
      'https://picsum.photos/200/300?random=2',
      'https://picsum.photos/200/300?random=3',
    ]"
  /> -->
  <converter />
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Converter from "./components/exe2/Converter.vue";

export default defineComponent({
  name: "App",
  components: {
    Converter,
  },
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>