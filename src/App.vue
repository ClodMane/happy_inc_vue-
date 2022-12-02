<template>
  <div id="app">
    <Card />
  </div>
</template>

<script>
import Card from "@/components/Card.vue";

export default {
  name: "AppVue",
  components: {
    Card,
  },
  data() {
    return {
      newObject: {},
    };
  },
  methods: {
    createNewObject(form) {
      this.newObject = form;
    },
  },
};
</script>

<style lang="scss">
@import "assets/index.css";
body {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100vh;
  font-family: Arial, sans-serif;
  background: grey;
}
*,
body {
  box-sizing: border-box;
}
</style>
