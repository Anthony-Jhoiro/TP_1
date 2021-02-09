<template>
  <input type="text" v-model="originValue" />
  <p>Origin</p>
  <div>
    <div>
      <input
        type="radio"
        name=""
        id="km"
        value="1000000"
        v-model="originMetter"
      /><label for="km">KM</label>
    </div>
    <div>
      <input
        type="radio"
        name=""
        id="m"
        value="1000"
        v-model="originMetter"
      /><label for="m">M</label>
    </div>
    <div>
      <input
        type="radio"
        name=""
        id="mm"
        value="1"
        v-model="originMetter"
      /><label for="mm">MM</label>
    </div>
  </div>
  <p>Destination</p>
  <div>
    <div>
      <input
        type="radio"
        name=""
        id="km"
        value="1000000"
        v-model="destinationMetter"
      /><label for="km">KM</label>
    </div>
    <div>
      <input
        type="radio"
        name=""
        id="m"
        value="1000"
        v-model="destinationMetter"
      /><label for="m">M</label>
    </div>
    <div>
      <input
        type="radio"
        name=""
        id="mm"
        value="1"
        v-model="destinationMetter"
      /><label for="mm">MM</label>
    </div>
  </div>
  <p>{{ destinationValue }}</p>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "converter",
  data() {
    return {
      originValue: "0",
      originMetter: "1000",
      destinationMetter: "1000",
      //   destinationValue: "0",
    };
  },
  computed: {
    destinationValue(): number {
      console.log(this.originValue, this.originMetter, this.destinationMetter);
      return (
        parseInt(this.originValue) *
        (parseInt(this.originMetter) / parseInt(this.destinationMetter))
      );
    },
  },
  //   watch: {
  //     originValue(n, o) {
  //       this.destinationValue = (
  //         parseInt(n) *
  //         (parseInt(this.originMetter) / parseInt(this.destinationMetter))
  //       ).toString();
  //     },
  //   },
});
</script>

<style>
</style>