<template>
  <div>
    <input type="text" placeholder="Name" v-model="name" />

    <input type="text" placeholder="ref First Name" v-model="firstName" />
    <input type="text" placeholder="ref Last Name" v-model="lastName" />

    <input type="text" placeholder="reactive First Name" v-model="fName" />
    <input type="text" placeholder="reactive Last Name" v-model="lName" />
    <input type="text" placeholder="reactive Hero Name" v-model="options.heroName" />
  </div>
</template>

<script>
import { ref, watch, reactive, toRefs } from "vue";
import _ from 'lodash'
export default {
  name: "WatchComp",
  setup() {
    const firstName = ref("");
    const lastName = ref("");
    watch(
      [firstName, lastName],
      (newValues, oldValues) => {
        console.log("FirstName Old value", oldValues[0]);
        console.log("FirstName New value", newValues[0]);
        console.log("LastName Old value", oldValues[1]);
        console.log("LastName New value", newValues[1]);
      },
      {
        immediate: true,
      }
    );

    const state = reactive({
      fName: "",
      lName: "",
      options: {
          heroName: ''
      }
    });
    // watch(
    //   () => {
    //     return { ...state };
    //   },
    //   function (newValue, oldValue) {
    //     console.log("fName Old value", oldValue.fName);
    //     console.log("fName New value", newValue.fName);
    //     console.log("lName Old value", oldValue.lName);
    //     console.log("lName New value", newValue.lName);
    //   }
    // );
    watch(
      () => _.cloneDeep(state.options),
      function (newValue, oldValue) {
        console.log("fName Old value", oldValue);
        console.log("fName New value", newValue);
      },
      {
          deep: true
      }
    );

    return {
      firstName,
      lastName,
      ...toRefs(state),
    };
  },
  data() {
    return {
      name: "",
    };
  },
  watch: {
    name(newValue, oldValue) {
      console.log("Old value", oldValue);
      console.log("New value", newValue);
    },
  },
};
</script>

<style scoped>
</style>