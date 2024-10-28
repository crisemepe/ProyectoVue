<script setup>
import logo from "/images/Logo-LBD.png";

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

  <v-header app>
    <v-toolbar class="menu">
      <v-menu transition="slide-y-transition">

        <template v-slot:activator="{ props }">
          <v-btn  color="white ml-6" v-bind="props"> Menú </v-btn>
        </template>

        <v-list class="desplegable">
          <v-list-item v-for="(item, i) in puntosmenu" :key="i">
            <v-list-item-title>{{ item.text }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>

      <v-toolbar-title class="d-flex justify-center mt-8 mb-6">
        <img :src="logo" alt="Logo" height="60" />
      </v-toolbar-title>

      <v-avatar color="white" class="mr-9">
      <v-icon icon="mdi-account-circle"></v-icon>
    </v-avatar>
    </v-toolbar>
  </v-header>
</template>
