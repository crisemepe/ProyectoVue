<script setup>
import logo from "@/assets/images/Logo-LBD.png";

const puntosmenu=[
  {
    "icon": "mdi-book",
    "text": "CARTA"
  },
  {
    "icon": "mdi-book-open",
    "text": "RESERVAS"
  },
  {
    "icon": "mdi-phone",
    "text": "CONTACTO"
  }
];
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
      <v-menu transition="slide-y-transition">
        <template v-slot:activator="{ props }">
          <v-btn color="primary" v-bind="props"> Menú </v-btn>
        </template>
        <v-list>
          <v-list-item v-for="(item, i) in puntosmenu" :key="i">
            <v-list-item-title>{{ item.text }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>

      <v-toolbar-title class="d-flex justify-center mt-8 mb-6">
        <img :src="logo" alt="Logo" height="60" />
      </v-toolbar-title>

      <!--<v-btn icon>
        <v-icon>mdi-account</v-icon>
      </v-btn>-->
      <v-avatar color="white" class="mr-9">
      <v-icon icon="mdi-account-circle"></v-icon>
    </v-avatar>
    </v-toolbar>
  </v-header>
</template>
