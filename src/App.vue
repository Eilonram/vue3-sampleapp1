<template>
  <click-counter />
  <hover-counter />
</template>
<script>
import ClickCounter from "./components/ClickCounter.vue";
import HoverCounter from "./components/HoverCounter.vue";
export default {
  name: "App",
  components: {
    ClickCounter,
    HoverCounter,
  },
  data() {
    return {};
  },
  methods: {},
  provide() {
    return {};
  },
};
</script>

<style >
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  /* font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin: 0;
  padding: 0;
  height: 100%; */
}
/* h4 {
  color: orange
} */
/* label {
  font-weight: bold;
  display: inline-flex;
  margin-right: 20px;
}
input + label {
  font-weight: bold;
  display: inline-flex;
  margin-right: 20px;
}
input[type="text"],
textarea,
select {
  display: block;
  width: 400px;
  padding: 6px, 12px;
  font-size: 14px;
  line-height: 1.42857143;
  color: #555;
  background-color: #fff;
  background-image: none;
} */
/* .container {
  height: 100%;
  display: grid;
  justify-content: center;
  align-items: center;
}

.content {
  max-width: 400px;
  position: relative;
} */
</style>
