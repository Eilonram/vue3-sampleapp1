<template>
  <div>
    <input type="text" placeholder="First Name" v-model="fname" />
    <input type="text" placeholder="Last Name" v-model="lname" />
    <h2>Options Fullname is {{ fullName }}</h2>

    <input type="text" placeholder="First Name" v-model="refFirstName" />
    <input type="text" placeholder="Last Name" v-model="refLastName" />
    <h2>Composition FullName is {{ refFullName }}</h2>

    <input type="text" placeholder="First Name" v-model="reactiveFirstName" />
    <input type="text" placeholder="Last Name" v-model="reactiveLastName" />
    <h2>Reactive FullName is {{ reactiveFullName }}</h2>
    
  </div>
</template>

<script>
import { ref, computed, reactive, toRefs } from "vue";
export default {
  name: "ComputedComp",
  setup() {
    const refFirstName = ref("");
    const refLastName = ref("");
    const refFullName = computed(function () {
      return `${refFirstName.value} ${refLastName.value}`;
    });

    const state = reactive({
        reactiveFirstName: '',
        reactiveLastName: ''
    })
    const reactiveFullName = computed(function() {
        return `${state.reactiveFirstName} ${state.reactiveLastName}`
    })

    return {
      refFirstName,
      refLastName,
      refFullName,
      ...toRefs(state),
      reactiveFullName
    };
  },
  data() {
    return {
      fname: "",
      lname: "",
    };
  },
  computed: {
    fullName() {
      return `${this.fname} ${this.lname}`;
    },
  },
};
</script>

<style scoped>
</style>