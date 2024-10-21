
<script>
import logo from '@/assets/images/Logo-Borracha-Designada.png';

export default {
  name: 'HeaderComponent',
  data() {
    return {
      logo,
    };
  },
}
</script>

<template>
 <!-- <v-header>
    <v-app-bar :elevation="2" rounded>
      <template v-slot:prepend>
        <v-app-bar-nav-icon></v-app-bar-nav-icon>
      </template>

      <v-app-bar-title>Application Bar</v-app-bar-title>
      <v-avatar color="surface-variant"></v-avatar>
    </v-app-bar>

  </v-header>
  -->

  <v-header app>
    <v-toolbar class="menu">
      <!-- Menú desplegable -->
      <v-menu offset-y>
        <template v-slot:activator="{on}">
          <v-btn text v-on="on">
            Menú
          </v-btn>
        </template>
        <v-list>
          <v-list-item>
            <v-list-item-title>CARTA</v-list-item-title>
          </v-list-item>
          <v-list-item>
            <v-list-item-title>RESERVAS</v-list-item-title>
          </v-list-item>
          <v-list-item>
            <v-list-item-title>CONTACTO</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>


      <v-toolbar-title class="d-flex justify-center">
        <img :src="logo" alt="Logo" height="70" />
      </v-toolbar-title>


      <!--<v-btn icon>
        <v-icon>mdi-account</v-icon>
      </v-btn>-->
      <v-avatar color="surface-variant"></v-avatar>
    </v-toolbar>
  </v-header>

</template>

