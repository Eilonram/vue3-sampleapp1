<template>
<div>
    <h2>
        Article Component
    </h2>
    <h2 v-bind="$attrs">{{title}}</h2>
    <h2>Likes - {{likes}}</h2>
    <h2>Published - {{isPublished ? 'Yes' : 'No'}}</h2>
</div>

</template>

<script>
    export default {
        name: 'ArticleComp',
        props: {
            title: {
                type: String,
                required: true,
            },
            likes: Number,
            isPublished: Boolean
        },
        inheritAttrs: false
    }
</script>

<style scoped>

</style>