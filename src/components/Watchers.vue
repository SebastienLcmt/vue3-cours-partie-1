<template>
    <h1>Les Watchers</h1>


    <h1> Volume Tracker (0 - 20)</h1>
    <h3> Current Volume {{ volume }} </h3>

    <button @click="volume += 2">Increase</button>
    <button @click="volume -= 2">Decrease</button>
    <br>
    <br>

    <input v-model="movie" type="text" />
    <br>
    <br>
    <input v-model="movieInfo.title" type="text" />
    <br>
    <input v-model="movieInfo.actor" type="text" />

</template>

     

<script>
    export default {
        data() {
            return {
                volume: 0,
                movie : 'Batman',
                movieInfo: {
                    title: '',
                    actor: '',
                }
            }
        },
        methods: {
            
        },

        //  Ici on surveille la variable volume de data. A chaque fois que sa valeur change, on peut exécuter une méthode

        watch: {
            // reçoit automatiquement la valeur mise à jour en paramètre (newValue), et l'ancienne en second paramètre
            volume(newValue, oldValue){  
                if(newValue > oldValue && newValue === 16) {
                     alert('Warning: the volume is super high')
                }
            },
            // Immediate watcher
            movie:{
                handler(newMovie){
                    console.log(newMovie);
                },
                immediate: true, // cela informe vue que la méthode handler doit être exécutée lors du premier chargement
            },
            movieInfo:{
                handler(newMovieInfo){
                    console.log(newMovieInfo.title, newMovieInfo.actor);
                },
                deep: true, // pour watch les changements sur une valeur de référence (objet ou tableau)
            }
        }
    }
    /* Computed properties : 
        - Compose new data from existing data sources
        - reduce the length of a variable

        WAtchers :
         - check if a property has reached a certain value to then perform an action
         - Call an APi in response to change in application data
         - If you have to apply transitions (watchers nous donne valeur de départ et de fin)
       
    */


</script>

<style scoped>

</style>