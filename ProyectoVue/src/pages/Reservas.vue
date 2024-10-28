<script setup>
import { ref } from "vue";

const firstNameRules = [
  (value) => {
    if (value?.length >= 3) return true;
    return "First name must be at least 3 characters.";
  },
];

const lastNameRules = [
  (value) => {
    if (/[^0-9]/.test(value)) return true;
    return "Last name can not contain digits.";
  },
];

const allowedDates = (val) => {
  const date = new Date(val);
  if (isNaN(date.getTime())) {
    return false; // Manejo de fechas inválidas
  }
  return date.getDate() % 2 === 0; // Verificar si el día es par
};

var formResult = ref({
  firstName:'',
  lastName:'',
  date:new Date("2024-10-24")
})

function resultados() {
  console.log(formResult.value.firstName + ',' + formResult.value.lastName + ',' + formResult.value.date)
}
</script>

<template>
  <v-sheet class="mx-auto" width="300">
    <v-form fast-fail @submit.prevent>
      <v-text-field
        v-model="formResult.firstName"
        :rules="firstNameRules"
        label="First name"
      ></v-text-field>

      <v-text-field
        v-model="formResult.lastName"
        :rules="lastNameRules"
        label="Last name"
      ></v-text-field>

      <v-container>
        <v-row justify="space-around">
          <v-date-picker
            v-model="formResult.date"
            :allowed-dates="allowedDates"
            max="2025-10-20"
            min="2024-10-15"
          ></v-date-picker>
        </v-row>
      </v-container>

      <v-btn class="mt-2" block @click="resultados()">Submit</v-btn>
    </v-form>
  </v-sheet>
</template>
