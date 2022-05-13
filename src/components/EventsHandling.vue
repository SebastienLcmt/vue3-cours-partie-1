<template>
    <h1> {{ name }} </h1>

    <button v-on:click="name = 'Batman'">Change name</button>
    

    <h1> {{ count }}</h1>
    <button @click="count++">+</button>
    <button @click="count--">-</button>

    <h1> {{ count }} </h1>

    <button @click="increment">increment</button>
    <button @click="decrement">decrement</button>

    <!--  Possibilité de faire plusieurs évènements d'un coup -->

    <br>
    <br>

    <button v-on:click="name = 'Batman', increment()">Change name + increment</button>
    
    <br>
    <br>
    <!--  Pour accéder à l'objet d'évènement -->

    <input @input="setMessage($event)" type="text" id="msg" placeholder="Your message here">
    <label for="msg">Message</label>
    <h1> {{ msg }}</h1>


</template>

<script>
export default {
    name : 'EventsHandling',
    data(){
        return {
            name : "Sébastien", 
            count: 0,
            msg: ''
        }
    },
    methods: {
        increment(){
            this.count++
        },
        decrement(){
            this.count--
        },
        setMessage(e){
            let newMsg = e.target.value;
            this.msg = newMsg;
        }
    }

}
</script>

<style>

</style>