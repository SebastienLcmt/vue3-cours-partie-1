<template>
  <h1 v-if="number === 0" >La condition est true</h1>
  <h1 v-else>La condition est false</h1>
  
  <template v-if="display">  
      <!--  template permet de display des éléments de même niveau sans avoir besoin de les entourer d'une balise  -->
      <h2>Salut</h2>
      <h2>hello</h2>
      <h2>Salut</h2>
  </template>

    <!--  Si v-show est false, l'élément reste dans le DOM et a un dispay none -->
  <h2 v-show="showElement">Title using v-show</h2>

  <!--  Avec v-if, l'élément disparait du DOM -->
  <h2 v-if="showElement">Title using v-if</h2>


  <!--  Si on veut toggle l'apparition d'un élément assez souvent, v-show sera plus performant  -->


</template>

<script>
export default {
    name: 'ConditionalRendering',
    data() {
        return {
            number : 2,
            display : true,
            showElement: false,
        }
    }
}
</script>

<style>

</style>