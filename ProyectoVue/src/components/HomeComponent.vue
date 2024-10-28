<script setup>
import { useRouter } from "vue-router";
import HeaderComponent from "./HeaderComponent.vue";
import { ref } from "vue";

const router = useRouter();

const menuItems = ref([
  { icon: 'mdi-book', text: 'CARTA', path: '/carta' },
  { icon: 'mdi-book-open', text: 'RESERVAS', path:'/reservas' },
  { icon: 'mdi-phone', text: 'CONTACTO', path:'/contacto' },
]);

const images = [  //Variable estática
    "/images/La-Borracha-Designada-Restaurant-entrada.jpg",
    "/images/La-Borracha-Designada-Restaurant-terraza.jpg",
    "/images/La-Borracha-Designada-Restaurant-salon.jpg",
    "/images/La-Borracha-Designada-Restaurant-sala.jpg"
    ]
var increxendo = ref(0); //Variable dinámica
function aumento() { //función para aumentar el número de increxendo
  increxendo.value++;
}

function cambioPagina(url){
  console.log('Cambiar de pagina')
  router.push(url)
}

</script>

<template>
  <HeaderComponent> </HeaderComponent>

  <v-container class="contenedor">
    <v-carousel>
      <v-carousel-item v-for="image in images":key="image" :src="image" cover
      ></v-carousel-item>
    </v-carousel>

   <!-- <v-row>
      <v-col>
        <v-label>{{increxendo}}</v-label>
        <v-btn @click="aumento()">Bunito</v-btn>
      </v-col>
    </v-row>-->
  </v-container>

  <v-container fluid class="text-center pa-4">
    <v-row justify="center">
      <v-col
        v-for="(item, index) in menuItems"
        :key="index"
        cols="4"
        class="d-flex flex-column align-center"
      >
        <v-btn icon @click="cambioPagina(item.path)">
          <v-icon>{{ item.icon }}</v-icon>
        </v-btn>
        <span>{{ item.text }}</span>
      </v-col>
    </v-row>
  </v-container>



  <FooterComponent> </FooterComponent>
</template>
