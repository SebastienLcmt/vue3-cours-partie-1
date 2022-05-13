

<template>
  <!-- <Bind /> -->
  <!-- <ConditionalRendering /> -->
  <!-- <List /> -->
  <!-- <Methods /> -->
  <!-- <EventsHandling /> -->
  <!-- <formHandling /> -->
  <!-- <ComputedProperties /> -->
  <!-- <Watchers /> -->
  <!-- <ComponentProps name="Sébastien" lastName="Chabal" />
  <ComponentProps name="John" />
  <ComponentProps name="Diane" />
  <ComponentProps :name="heroName" /> -->
  <!-- <PropType id="article" title="Article Title" :likes="50" :isPublished="true"/> -->
  <!-- <ProvideAndInject /> -->
    <!-- <PopupParent /> -->
    <!-- <Input v-model="name"/> -->
        <!-- <Slots>Card Content</Slots>
        <Slots></Slots>
        <Slots>
          <h2>Card Content in title</h2>
        </Slots>
        <Slots><img src="https://i.picsum.photos/id/609/200/200.jpg?hmac=Fe1MOOyr8RJSloodBDzO2oMGF2NvnJVhuoGNDTC5clU"></Slots>
        <Slots>
          <template v-slot:header> 
            <h3>Title for this specified slot</h3>    
          </template>
          <template v-slot:default>
            Contenu du slot par défaut     
          </template>
        </Slots> -->

            <!-- Pour récupérer les props -->
        <!-- <Slots>
          <template v-slot:default="slotProps">
              {{ slotProps.firstName }} {{ slotProps.lastName }}
          </template>
        </Slots>

        <Slots>
          <template v-slot:default="slotProps">
              {{ slotProps.firstName }}
          </template>
        </Slots>  -->

        <!--  Dynamic components -->
  <!-- <button @click="activeTab = 'TabA'">Tab A</button>
  <button @click="activeTab = 'TabB'">Tab B</button>
  <button @click="activeTab = 'TabC'">Tab C</button>
  <keep-alive>
    <component :is="activeTab" />
  </keep-alive> -->
  <!-- Si on écrit dans le tabC, on retrouvera la donnée -->
  <!-- <teleport to="#portal-root">
    <TeleportComponent />
  </teleport> -->

  <div></div>
</template>

<script>
// import Bind from './components/Bind'
// import ConditionalRendering from './components/ConditionalRendering'
// import List from './components/ListRendering.vue'
// import Methods from './components/Methods.vue'
// import EventsHandling from './components/EventsHandling.vue'
// import formHandling from './components/formHandling.vue'
// import ComputedProperties from './components/ComputedProperties.vue'
// import Watchers from './components/Watchers.vue'
// import ComponentProps from "./components/ComponentProps.vue";
// import PropType from "./components/PropType.vue";
// import ProvideAndInject from "./components/ProvideAndInject.vue";
// import PopupParent from "./components/Popup/PopupParent.vue";
// import Input from "./components/Input.vue";
// import Slots from "./components/Slots.vue";
// import TabA from './components/DynamicComponents/TabA.vue'
// import TabB from './components/DynamicComponents/TabB.vue'
// import TabC from './components/DynamicComponents/TabC.vue'
// import TeleportComponent from "./components/TeleportComponent.vue";

export default {
  name: "App",
  data() {
    return {
      // heroName: 'Batman',
      // username : "Seballo",
      // name: '',
      // activeTab : 'TabA'
    }    
  },
  components: {
    // Bind,
    // ConditionalRendering,
    // List,
    // Methods,
    // EventsHandling,
    // formHandling,
    // ComputedProperties,
    // Watchers,
    // ComponentProps,
    // PropType,
    // ProvideAndInject,
    // PopupParent,
    // Input,
    // Slots,
    // TabA,
    // TabB,
    // TabC,
    // TeleportComponent,
  },
  // Si pas besoin d'utiliser une donnée dans ce composant, on peut juste spécifier provide en tant qu'objet
  // provide : {}
  provide() {
    return {
      // userName : this.username // de cette manière on peut aussi utiliser userName dans ce composant
    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #333;
  margin-top: 60px;
}
</style>
