

<template>
  <div>
    <h1>{{ name }}</h1>
    <h1 v-html="lastname"></h1>
    <h2 v-bind:class="condition && style"> Underlined text</h2> 
    <h2 v-bind:class="{
      'sold-out':  isSoldOut,
      recent : isRecent,

    }">Sold out?</h2>

    <h3 v-bind:style="{
      color : 'lightblue',
    }">Inline style</h3>

    <h4 :style="headerStyleObject"> Style lié depuis objet dans Data()</h4>

  </div>
</template>

<script>
export default {
  name: 'Bind',
  data(){
    return {
      name: 'Sébastien',
      lastname: '<i> Chabal </i>',
      style: 'underlined',
      condition: true,
      isSoldOut : true,
      isRecent : true,
      headerStyleObject: {
        color: 'green',
        fontSize: '50px',
        padding : '20px',
        margin: 0
      }
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.underlined {
  text-decoration: underline;
}

.sold-out {
  color : crimson;
}
.recent {
  font-family: fantasy;
}
</style>
