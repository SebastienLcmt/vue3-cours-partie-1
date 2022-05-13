<template>
    <h1> {{ userName }} </h1>
</template>

<script> // Imaginons que ce composant ne soit pas un enfant direct de APP
    export default {
        name: "ProvideAndInject",
        data() {
            return {
                
            }
        },
        inject: ['userName'] // récupéré depuis provide dans App.vue
    }
</script>

<style scoped>

</style>