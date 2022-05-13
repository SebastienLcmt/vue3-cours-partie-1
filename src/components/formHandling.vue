<template>
  <h1>Handling forms</h1>

  <form action="" @submit="submitForm">
  <!-- <form action="" @submit.prevent="submitForm"> --> 
    <div>
      <label for="name">Name</label>
      <!-- .trim enlève les espaces en trop en début et fin de chaine de caractères -->
      <!-- .lazy met à jour la variable name seulement quand l'évènement change a lieu (quand on perd le focus sur l'input). Cela améliore les performances légèrement, et est mieux pour la validation -->
      <input type="text" id="name" v-model.trim.lazy="formValues.name" />
      <br>
      <!-- .number assure que la valeur rentrée dans l'input soit de type number -->
      <input type="number" id="age" v-model.number="formValues.age" />
    </div>
    <div>
      <label for="profile">Profile Summary</label>
      <textarea type="text" id="profile" v-model="formValues.profileSummary" />
    </div>
    <!-- Select -->
    <div>
        <label for="country">Country</label>
        <select name="country" id="country" v-model="formValues.country">
            <option value="">Select a country</option>
            <option value="france">France</option>
            <option value="england">England</option>
            <option value="sweden">Sweden</option>
        </select>
    </div>
    <!-- Select multiple choices -->
    <div>
        <label for="location">Job Location</label>
        <select name="location" id="location" multiple v-model="formValues.jobLocation" >
            <option value="">Select a country</option>
            <option value="france">France</option>
            <option value="england">England</option>
            <option value="sweden">Sweden</option>
        </select>
    </div>

    <!-- Checkbox -->
    <div>
        <input type="checkbox" id="remoteWork" v-model="formValues.remoteWork" true-value="yes" false-value="no">
        <label for="remoteWork"> Open to remote work ?</label>
    </div>

    <!-- Multiple checkboxes -->
    <br>
    <div>
        <h4> Skillset </h4>
<br>
<br>
        <input type="checkbox" name="html" id="html" value="html" v-model="formValues.skillSet">
        <label for="html">html</label>

        <input type="checkbox" name="css" id="css" value="css" v-model="formValues.skillSet">
        <label for="css">css</label>

        <input type="checkbox" name="javascript" id="javascript" value="javascript" v-model="formValues.skillSet">
        <label for="javascript">javascript</label>
      
    </div>

<br>
<!-- Radio -->
    <div>
        <h4> Skillset </h4>
<br>
        <input type="radio"  id="0-2" value="0-2" v-model="formValues.yearsOfExperience">
        <label for="0-2">0-2</label>

        <input type="radio" id="3-5" value="3-5" v-model="formValues.yearsOfExperience">
        <label for="3-5">3-5</label>

        <input type="radio"  id="6-10" value="6-10" v-model="formValues.yearsOfExperience">
        <label for="6-10">6-10</label>
      
    </div>
    
    
    <button>Submit</button>

  </form>

  <pre>
        {{ JSON.stringify(formValues, null, 2) }}
    </pre>
</template>

<script>
export default {
  data() {
    return {
      formValues: {
        name: "",
        profileSummary: '',
        country: '',
        jobLocation : [],
        remoteWork: "no",
        skillSet: [],
        yearsOfExperience: '',
        age: null,
      },
    };
  },
  methods: {
      submitForm(event) {
          event.preventDefault();
          console.log(this.formValues);
      }
  },
};
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  color: #333;
}

h1 {
  margin-bottom: 30px;
}

label, div {
  margin: 20px;
}
</style>