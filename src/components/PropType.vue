<template>
    
  <div> 
    <h1>{{ title }}</h1>
    <!-- ici l'attribut id passé en props sera mis sur le h2 ET sur la div englobante, sauf si inheritAttrs est false -->
    <h2 v-bind="$attrs">Nombre de likes : {{ likes }}</h2>

    <h2>Published : {{ isPublished ? "Yes" : "No" }}</h2>
  </div>
</template>

<script>
export default {
  name: "PropType",
  props: {
    // title : String,
    title: {
      type: String,
      required: true,
      default: "Article default title",
    },
    likes: Number, // dans App.vue, on a bind la prop afin de spécifier à vue que la prop doit être considérée comme de type de number, sinon ce serait une string
    isPublished: Boolean,
  },
  inheritAttrs: false,
//   <!-- Pour les non-props attributes (id, class, etc..)  vue les transmets automatiquement sur la balise englobante, ici la div.  Si l'on ne veut pas de ça, mettre inheritAttrs à false -->
};
</script>

<style scoped>
</style>