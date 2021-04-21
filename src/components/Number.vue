<template>
  <div>
    <input type="button" @click="clickElement(numero)" v-bind:value="numero">
  </div>
</template>

<script>
export default {
  name: "Numbers",
  props: ["numero"],
  methods: {
    clickElement: function(element) {
      this.$emit("element-clickat", element);
    }
  }
};
</script>

<style scoped>
</style>