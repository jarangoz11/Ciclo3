<template>


  <v-app id="inspire">

    <encabezado :title="title" :drawer="drawer" />
    <v-navigation-drawer v-model="drawer" app>
      <Menu :title="title" :isAdmin="true" />
    </v-navigation-drawer>

    
        
    <v-footer app>
      <Footer />
    </v-footer>    
  </v-app>
</template>

<script>


import Encabezado from "./components/Encabezado.vue"
import Footer from "./components/Footer.vue"
import Menu from "./components/Menu.vue"



export default {
  name: 'App',

  components: {
    Encabezado,
    Menu,  
    Footer,
  },

    
   data() {
    return {      
      title: "Vitrina Agrícola",
      drawer: true,
    };
  },
  watch: {
    drawer(value) {
      return value;
    },
  },
};
</script>
