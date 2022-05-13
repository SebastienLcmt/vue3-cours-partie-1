<template>
    <h1> Salut {{ name }} {{ lastName }} </h1>
</template>

<script>
    export default {
        name: 'ComponentProps',
        data() {
            return {
                
            }
        },
        props: ['name', 'lastName']
    }
</script>

<style scoped>

</style>