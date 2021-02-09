<template>
  <div v-if="imageList.length != 0">
    <img :src="imageList[currentIndex]" alt="" />
  </div>
  <button @click="previous">Previous</button>
  <button @click="next">Next</button>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "carousel",
  props: {
    imageList: { type: Array, required: true },
  },
  data() {
    return {
      currentIndex: 0,
    };
  },
  methods: {
    next() {
      if (this.currentIndex == this.imageList.length - 1) {
        this.currentIndex = 0;
      } else this.currentIndex++;
    },
    previous() {
      if (this.currentIndex == 0) {
        this.currentIndex = this.imageList.length - 1;
      } else this.currentIndex--;
    },
  },
});
</script>

<style>
</style>