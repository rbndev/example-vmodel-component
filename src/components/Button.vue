<template>
  <button :class="color">{{ label }}</button>
</template>

<script>
import { ref } from "vue";

export default {
  props: ["label", "color"],
  setup() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=Roboto&display=swap");

button {
  font-family: "Roboto", sans-serif;
  font-size: 15px;
  font-weight: bold;
  margin: 0;
  border: none;
  padding: 10px 50px;
  border-radius: 8px;
  cursor: pointer;
}
.primary {
  color: #ededed;
  background: #646363;
  &:hover {
    box-shadow: 0 0 6px 0px #646363;
  }
}
.secondary {
  padding: 10px 30px;
  &:hover {
    box-shadow: 0 0 6px 0px #646363;
  }
}
</style>