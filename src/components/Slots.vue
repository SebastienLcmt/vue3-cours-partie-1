<template>
  <!-- <div class="card">
      <div class="card-header">
          <slot name="header"></slot>
      </div>
    <div class="card-content">
      <slot>Default content here</slot>
    </div>
  </div> -->

    <!-- Pour passer des props au slots -->

    <div class="card">
        <h3 v-for="name in names" :key="name">
            <slot :firstName="name.firstName" :lastName="name.lastName"></slot>
        </h3>    
    </div>
 

</template>

<script>
export default {
  name: "Slots",
  data() { // passer des props aux slots
    return {
        names: [
            {
                firstName : 'Séb',
                lastName : "Chabal",
            },
            {
                firstName : 'Marie',
                lastName : "Curry",
            },
        ]
    };
  },
};
</script>

<style scoped>
.card {
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  transition: 0.3s;
  padding: 16px;
  margin-bottom: 20px;
  width: 200px;
  height: auto;
  background: #222;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}
</style>