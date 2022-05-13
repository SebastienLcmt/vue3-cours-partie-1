<template>
    <h2> {{ fullName }}</h2>

    <button @click="changeFullName"> Change FullName </button>

    <template v-for="item in items" :key='item.id'> 
          <h2 v-if="item.price > 100"> {{ item.title }} {{ item.price }} </h2>        
    </template>

    <!-- Meilleure façon de faire. Si changement dans la page, vue ne recalculera pas -->
    <h2 v-for="item in expensiveItems" :key="item.id" > {{ item.title }} {{ item.price }} </h2>

</template>

<script>
    export default {
        name: 'ComputedProperties',
        data() {
            return {
                firstName : "Bruce",
                lastName: "Wayne",
                items: [
                    {
                        id: 1,
                        title: 'TV',
                        price: '100'
                    },
                    {
                        id: 2,
                        title: 'phone',
                        price: '200'
                    },
                    {
                        id: 3,
                        title: 'laptop',
                        price: '400'
                    },
                ]
            }
        },
        methods: {
            changeFullName() {
                this.fullName = 'Clark Kent'
            }
        },

        // les computed properties sont mises en cache.
        // Si une method fait exactement la meme chose qu'une computed property, et qu'il y a un changement dans le composant, la méthode sera réexécutée pour chaque changement. Mais pas la computed property.
        // La mise en cache permet une meilleure performance en évitant de réexécuter du code inutilement

        computed:{
            fullName: {
                get() {
                    return `${this.firstName} ${this.lastName}`
                },
                set(value) {
                    const names = value.split(' ');
                    this.firstName = names[0];
                    this.lastName = names[1];
                }
                
            },
            expensiveItems(){
                return this.items.filter(item => item.price > 100)
            }
        }
    }
</script>

<style scoped>

</style>