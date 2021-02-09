<template>
  <form v-if="formSubmited">
    <input type="text" v-model="firstName" />
    <input type="text" v-model="lastName" />
    <input type="text" v-model="mail" />
    <input type="date" v-model="date" name="" id="" />
    <button @click="formSubmited = true"></button>
  </form>

  <p v-if="!formSubmited">Félicitations, vous êtes inscrits</p>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "register-form",
  data() {
    return {
      formSubmited: false,
      lastName: "",
      firstName: "",
      date: "",
      mail: "",
    };
  },
  methods: {
    validForm(): void {
      this.formSubmited =
        this.firstName.length > 0 &&
        this.lastName.length > 0 &&
        this.validEmail(this.mail);
    },
    validEmail: function (email: string): boolean {
      var re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
      return re.test(email);
    },
  },
});
</script>

<style>
</style>