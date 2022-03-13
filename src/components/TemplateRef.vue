<template>
    <div>
        <input type="text" ref="inputRef"/>
        <!-- <post-list ref="postlistRef"/> -->
    </div>
</template>

<script>
import {ref, onMounted} from 'vue'
    export default {
        name: 'TemplateRef',
        setup(){
            const inputRef = ref(null)

            onMounted(() => {
                inputRef.value.focus()
            }) 

            return {
                inputRef
            }
        },
        //mounted() {
            //console.log(this.$refs.postlistRef)
            //this.$refs.inputRef.focus()
        //}
    }
</script>

<style scoped>

</style>