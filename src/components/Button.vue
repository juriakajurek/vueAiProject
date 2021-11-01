<template>
  <button :class="{ 'big-button': bigbutton }" @click="$emit('button-click')">
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "Button",
  props: {
    text: String,
    bigbutton: Boolean,
  },
};
</script>

<style scoped lang="less">
button {
  margin: 0.5rem;
  color: white;
  font-size: 0.675rem;
  background-color: #404e40;
  border-radius: 0.5rem;

  padding-top: 0.3rem;
  padding-bottom: 0.3rem;
  padding-left: 3rem;
  padding-right: 3rem;

  cursor: pointer;
  &.big-button {
    width: 95%;
    padding-top: 0.5rem;
    padding-bottom: 0.5rem;
  }
}
</style>