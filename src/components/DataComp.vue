<template>
    <h2>Options - {{o_firstName}}</h2>
    <h2>Options - {{o_firstName}} {{o_lastName}} a.k.a {{o_heroName}}</h2>
    <h2>Composition- {{c_firstName}}</h2>
    <h2>Composition- {{c_firstName}} {{c_lastName}} a.k.a {{c_heroName}}</h2>
    <h2>Composition- {{greetHero}}</h2>

    <h2>Reactive- {{state.firstName}} {{state.lastName}} a.k.a {{state.heroName}}</h2>
    <h2>Reactive- {{reactiveGreetHero}}</h2>
</template>

<script>
import {ref, reactive} from 'vue'
    export default {
        name: 'DataComp',
        setup() {
            const c_firstName = ref('Clark') 
            const c_lastName = ref('Kent') 
            const c_heroName = ref('Superman') 
            
            const greetHero = `Hello ${c_firstName.value} ${c_lastName.value} a.k.a ${c_heroName.value}`
    
            const state = reactive({
                firstName: 'Princess',
                lastName: 'Diana',
                heroName: 'Wonder Woman'
            })
            const reactiveGreetHero = `Hello ${state.firstName} ${state.lastName} a.k.a ${state.heroName}` 

            return {
                c_firstName,
                c_lastName,
                c_heroName,
                greetHero,
                state,
                reactiveGreetHero
            }
        },
        data() {
            return {
                o_firstName: 'Bruce',
                o_lastName: 'Wayne',
                o_heroName: 'Batman'
            }
        }
    }
</script>

<style scoped>

</style>