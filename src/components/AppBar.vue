<template>
  <div>
    <v-app id="inspire">
      <v-app-bar app color="cyan darken-3" dark>
        <v-app-bar-nav-icon @click.stop="drawer = !drawer"/>
        <v-toolbar-title>Trukilapp</v-toolbar-title>
      </v-app-bar>

      <v-navigation-drawer v-model="drawer" app>
        <v-list dense>
          <v-list-item link>
            <v-list-item-action>
              <v-icon>mdi-home</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>Inicio</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
          <v-list-item link>
            <v-list-item-action>
              <v-icon>mdi-email</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>Contacto</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
    </v-app>
  </div>
</template>

<script>
export default {
  props: {
    source: String,
    drawer: null
  },
  data: () => ({
    drawer: null,
  }),
};
</script>