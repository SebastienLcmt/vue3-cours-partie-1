<template>
    
    <h1>List rendering</h1>

    <h2 v-for="(name,index) in list" :key="index">{{ name }}</h2>
    <!-- bind une key à chaque élément de la liste est important pour le fonctionnement de vue -->

    <h2 v-for="(name,index) in fullNames" :key="index"> {{ name.first}} {{ name.last }} </h2>

    <template v-for="(actor, index) in actors" :key="index"> 
        <h2>{{ actor.name }}</h2>
        <h3 v-for="(movie,index) in actor.movies" :key="index"> {{movie}}</h3>
    </template>
    
    <h3 v-for="(value,key,index) in moreData" :key="index"> {{ key  }} ---> {{ value }} </h3>

    <template v-for="(item, index) in list" :key="index">
        <h3 v-if="item === 'Pierre'"> {{ item }}</h3>
    </template>


</template>

<script>
export default {
    name: 'ListRendering',
    data(){
        return {
            list: ['Pierre', 'Paul', 'Jacques'],
            fullNames: [
                {first: "Jean", last: 'Bon'},
                {first: "Camille", last: 'Honette'},
                {first: "Mac", last: 'Ekete'},
            ],
            actors: [
                {
                    name: 'Christian Bale',
                    movies:  ['The Prestige', 'Batman']
                },
                {
                    name: 'Di Caprio',
                    movies:  ['Django', 'Inception']
                }
            ],
            moreData: {
                prenom : 'bernard',
                nom: 'chanel',
                age: '45'
            }
        }
    }

}
</script>


<style>

</style>