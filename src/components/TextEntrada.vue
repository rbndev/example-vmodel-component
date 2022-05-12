<template>
  <div class="flex flex-column">
    <p>{{ label }} <span class="required" v-if="required">*</span></p>
    <!-- TODO: input label -->
    <input :type="type" :placeholder="placeholder" v-model="inputValue" @input="$emit('update:vmodel', $event.target.value)" />
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  props: ["label", "required", "type", "placeholder", "vmodel"],
  setup() {
    const inputValue = ref()
    
    return {inputValue};
  },
};
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=Roboto&display=swap");
.flex {
  display: flex;
}
.flex-column {
  flex-direction: column;
  justify-content: space-around;
}
p {
  font-family: "Roboto", sans-serif;
  font-size: 15px;
  font-weight: bold;
  color: #646363;
  margin: 0;
  .required{
      color: rgb(207, 17, 17);
  }
}
input {
  margin: 8px 0 16px;
  border: none;
  height: 35px;
  border-radius: 8px;
  background: #646363;
  outline: none;
  color: #ededed;
  padding: 0 10px;
  font-family: "Roboto", sans-serif;
  font-size: 14px;
  font-weight: 500;
  letter-spacing: 1.6px;
  &:focus{
    box-shadow: 0 0 6px 0px #646363;
  }
}
</style>