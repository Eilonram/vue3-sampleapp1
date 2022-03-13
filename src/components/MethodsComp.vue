<template>
    <div>
        <h2>{{name}}</h2>
        <button @click="setName">Change Name</button>

        <h2>{{count}}</h2>
        <button @click="incrementCount">Increment Count</button>

        <h2>{{first}} {{last}}</h2>
        <button @click="changeHero">Change Hero</button>
    </div>
</template>

<script>
import {ref, reactive, toRefs} from 'vue'
    export default {
        name: 'MethodsComp',
        setup(){
            const count = ref(0)

            function incrementCount() {
                count.value++
            }
         
            const state = reactive({
                first: 'Clark',
                last: 'Kent'
            })
            function changeHero() {
                state.first = 'Princess'
                state.last = 'Diana'
            }
            return {
                count,
                incrementCount,
                ...toRefs(state),
                changeHero
                
            }
        },
        data() {
            return {
                name: 'Bruce',
            }
        },
        methods: {
            setName() {
                this.name ="Clark"
            }
        }
    }
</script>

<style scoped>

</style>