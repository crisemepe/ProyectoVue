<script setup>
import { ref } from "vue";
</script>

<template>
  <div>
    <v-expansion-panels>
      <v-expansion-panel
        v-for="i in 9"
        :key="i"
      >
      <v-expansion-panel-title>
        Entrante {{i}}
      </v-expansion-panel-title>

      <v-expansion-panel-text>
        <v-row class="align-center">
          <v-col class="d-flex justify-start align-center" cols="auto">
          <v-img
            :src="`/images/LBD-plato-${i}.jpg`"
            alt="Imagen plato"
            height="130"
            width="250"
            class="mr-2"
          />
        </v-col>
        <v-col class="d-flex align-center">
       <p> Lorem ipsum dolor sit amet, consectetur adipiscing elit,
        sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
        </v-col>
        </v-row>
      </v-expansion-panel-text>

    </v-expansion-panel>
    </v-expansion-panels>
  </div>

  <!--
  <div class="text-subtitle-2 mb-2">Entrantes</div>
<v-expansion-panels>
  <v-expansion-panel v-for="i in 10" :key="i">
    <template v-slot:header>
      <div>Entrante {{ i }}</div>
    </template>
    <v-expansion-panel-content>
      <v-row class="align-center">
        <v-col class="d-flex justify-start align-center" cols="auto">
          <v-img
            :src="`/images/LBD-plato${i}.jpg`"
            alt="Imagen plato"
            width="24"
            height="24"
            class="mr-2"
          />
        </v-col>
        <v-col class="d-flex align-center">
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
            eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut
            enim ad minim veniam, quis nostrud exercitation ullamco laboris
            nisi ut aliquip ex ea commodo consequat.
          </p>
        </v-col>
      </v-row>
    </v-expansion-panel-content>
  </v-expansion-panel>
</v-expansion-panels>
--></template>
