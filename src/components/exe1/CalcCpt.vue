<template>
  <button @click="calc">Validate</button>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "calc-cpt",
  props: {
    t1: Number,
    t2: Number,
    op: String,
  },
  methods: {
    calc() {
      //@ts-ignore
      this.$emit("result", eval(this.t1?.toString(10) + this.op + this.t2));
    },
  },
});
</script>

<style>
</style>