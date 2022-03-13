<template>
  <h2>Child A</h2>
  <child-b />
</template>

<script>
import ChildB from "./ChildB.vue";
export default {
  name: "ChildA",
  components: {
    ChildB,
  },
};
</script>

<style scoped>
</style>