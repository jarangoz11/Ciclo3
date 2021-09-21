<template>
  
    <div>
    <v-list-item>
      <v-list-item-content>
        <v-list-item-title class="text-h6"> {{ title }} </v-list-item-title>
        <v-list-item-subtitle> {{ subtitle }} </v-list-item-subtitle>
      </v-list-item-content>
    </v-list-item>

    <v-divider></v-divider>

    <v-list dense nav v-if="isAdmin">
      <v-list-item v-for="item in adminItems" :key="item.title" link :to="item.path">
        <v-list-item-icon>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-item-icon>

        <v-list-item-content>
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>

    <v-list dense nav>
      <v-list-item v-for="item in items" :key="item.title" link :to="item.path">
        <v-list-item-icon>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-item-icon>

        <v-list-item-content>
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </div>

</template>

<script>
export default {
name: "Menu",
  props: ["title", "isAdmin"],
  data() {
    return {
      subtitle: "Menu principal",
      adminItems: [
          { title: "Administrador", icon: "mdi-archive-settings" , path: "/catalog"},
          
          ],
      items: [
        { title: "Panel de control Expositores", icon: "mdi-home", path: "/Exposit/ExpositInfo" },
        { title: "Acerca de", icon: "mdi-help-box", path: "/about" },
        { title: "Búsqueda", icon: "mdi-home", path: "/Busqueda" },
        { title: "Inicio", icon: "mdi-home", path: "/" },
      ],
    };
  },
}
</script>

<style>

</style>