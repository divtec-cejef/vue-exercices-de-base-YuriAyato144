<template>
  <v-container max-width="700">
    <exercice-objectifs number="1"/>
    <div class="exe-zone">
      <h2>Zone d'exercice</h2>

      <v-card class="mx-auto my-6 pa-2" max-width="400">
        <v-card-title>{{ title }}</v-card-title>

        <v-card-subtitle :style="{ color: isHighlighted ? 'blue' : 'black' }">
          {{ description }}
        </v-card-subtitle>

        <v-card-actions>
          <v-btn color="primary" @click="toggleHighlight">
            Mettre en surbrillance
          </v-btn>
        </v-card-actions>
      </v-card>
    </div>
  </v-container>
</template>

<script setup>
import { ref } from "vue";
import ExerciceObjectifs from "@/components/ExerciceObjectifs.vue";

const title = "Bienvenue à l'exercice 1";
const description = "Cet exercice teste le rendu déclaratif et les liaisons d'attributs.";
const isHighlighted = ref(false);

function toggleHighlight() {
  isHighlighted.value = !isHighlighted.value;
}
</script>
