<template>
    <h1> Methods </h1>

    <h2> {{ add(5,10,64) }}</h2>

    <h2> {{ multiply(10) }}</h2>
</template>

<script>
export default {
    name: 'Methods',
    data(){
        return {
            multiplier : 5,
        }
    },
    methods: {
        add(a, b, c) {
            return a + b + c;
        },
        multiply (num) {
            return num * this.multiplier;
        }
        
    },
}
</script>

<style>

</style>