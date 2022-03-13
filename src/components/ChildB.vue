<template>
  <h2>Child B</h2>
  <child-c />
</template>

<script>
import ChildC from "./ChildC.vue";
export default {
  components: { ChildC },
  name: "ChildB",
};
</script>

<style scoped>
</style>