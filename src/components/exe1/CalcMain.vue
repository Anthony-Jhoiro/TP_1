<template>
  <div>
    <input type="number" v-model="t1" />
    <input type="text" v-model="op" />
    <input type="number" v-model="t2" />
  </div>
  <calc-cpt @result="setRes" :t1="t1" :t2="t2" :op="op" />
  <p>{{ message }}</p>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import CalcCpt from "./CalcCpt.vue";

export default defineComponent({
  name: "calc-main",
  data() {
    return {
      t1: 0,
      t2: 0,
      op: "+",
      message: "",
    };
  },
  components: {
    CalcCpt,
  },
  methods: {
    setRes(message: string) {
      this.message = message;
    },
  },
});
</script>

<style>
</style>