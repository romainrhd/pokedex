<script setup>
import { ref } from "vue";
import IconPokeball from "./icons/IconPokeball.vue";

const props = defineProps(["pokemon"]);
const shinyShowed = ref(false);
const currentAppearance = ref(props.pokemon.appearances[0]);

function toggleAppearance(appearanceId) {
  currentAppearance.value = props.pokemon.appearances.find(
    (appearance) => appearance.id === appearanceId
  );
}

function toggleShiny() {
  shinyShowed.value = !shinyShowed.value;
}
</script>

<template>
  <div class="relative flex flex-col basis-1/2 shadow-xl rounded-lg bg-white">
    <div class="absolute px-2 py-2 right-0">
      <font-awesome-icon
        class="text-gray-400 cursor-pointer"
        :class="{ 'text-yellow-300': shinyShowed }"
        :icon="['fas', 'star']"
        @click="toggleShiny"
      />
      <IconPokeball
        v-if="
          shinyShowed
            ? currentAppearance.shiny.catched
            : currentAppearance.catched
        "
      />
    </div>
    <img
      :src="
        shinyShowed ? currentAppearance.shiny.image : currentAppearance.image
      "
      :alt="currentAppearance.category"
    />
    <h3 class="text-center">
      #{{ pokemon.nationalNumber + " " + pokemon.name }}
    </h3>
    <div class="flex flex-wrap justify-center py-2">
      <span v-for="appearance in pokemon.appearances" :key="appearance.id">
        <span
          v-if="pokemon.appearances.length > 1"
          class="w-1/3 text-center cursor-pointer"
          :class="{
            'font-bold': appearance.category === currentAppearance.category,
          }"
          @click="toggleAppearance(appearance.id)"
          >{{
            appearance.category.charAt(0).toUpperCase() +
            appearance.category.slice(1)
          }}</span
        >
      </span>
    </div>
  </div>
</template>
