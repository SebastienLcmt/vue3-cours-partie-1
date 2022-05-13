<template>
    <input type="text" :value="modelValue" @input="$emit('update:modelValue', $event.target.value)"/>
    <!--  lors d'un update sur l'input, on envoie au parent les données de l'input -->
</template>

<script>
    export default {
        name: 'Input',
        props: {
            modelValue : String,
        }
    }
</script>

<style scoped>

</style>