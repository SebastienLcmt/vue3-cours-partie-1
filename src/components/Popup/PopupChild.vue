<template>
  <h1>This is a PopUp</h1>
  <input v-model="name" type="text" />
  <button @click="$emit('close', name)">Close Popup</button>
  <!-- le deuxième argument est les données que l'on veut faire remonter -->
</template>

<script>
    export default {
        name: 'PopupChild',
        // emits: ['close'], // tableau contenant la liste des évènements à faire remonter
        emits: {
            close : (name) => { // pour valider données remontées
                if(!name) {
                    return true
                }
                else {
                return false
            }
        }
        },
        data() {
            return {
                name : ''
            }
        },
    }
</script>
<style scoped>
</style>