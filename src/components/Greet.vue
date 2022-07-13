<template>
    <div>
        <h2>hello {{name}} a.k.a {{title}}</h2>
    </div>
</template>

<script>
    export default {
        name: 'GreetVue',
        props: ["name", "title"]
    }
</script>

<style scoped>

</style>