<script setup>
import HeaderComponent from "./HeaderComponent.vue";
import {ref} from "vue";

const images = [  //Variable estática
    "https://cdn.vuetifyjs.com/images/cards/docks.jpg",
    "https://cdn.vuetifyjs.com/images/cards/hotel.jpg",
    "https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
    ]
var increxendo = ref(0); //Variable dinámica
function aumento() { //función para aumentar el número de increxendo
  increxendo.value++;
}
</script>

<style lang="scss">
@import '../styles/style.scss';
</style>

<template>
  <HeaderComponent> </HeaderComponent>

  <v-container class="contenedor">
    <v-carousel>
      <v-carousel-item v-for="image in images":key="image" :src="image" cover
      ></v-carousel-item>
    </v-carousel>
    <v-row>
      <v-col>
        <v-label>{{increxendo}}</v-label>
        <v-btn @click="aumento()">Bunito</v-btn>
      </v-col>
    </v-row>

  </v-container>

  <FooterComponent> </FooterComponent>
</template>
