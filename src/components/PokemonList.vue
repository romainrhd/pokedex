<script setup>
import { ref } from "vue";
import PokemonCard from "@/components/PokemonCard.vue";

const pokemons = ref([
  {
    id: 1,
    name: "Bulbizarre",
    nationalNumber: "001",
    appearances: [
      {
        id: 1,
        category: "normal",
        image: "https://www.pokepedia.fr/images/f/f3/Sprite_001_EB.png",
        catched: true,
        type: [
          {
            name: "Plante",
          },
        ],
        shiny: {
          id: 2,
          category: "shiny",
          image:
            "https://www.pokepedia.fr/images/f/f7/Sprite_001_chromatique_EB.png",
          catched: false,
          type: [
            {
              name: "Plante",
            },
          ],
        },
      },
    ],
  },
  {
    id: 2,
    name: "Salamèche",
    nationalNumber: "004",
    appearances: [
      {
        id: 3,
        category: "normal",
        image: "https://www.pokepedia.fr/images/0/04/Sprite_004_EB.png",
        catched: true,
        type: [
          {
            name: "Feu",
          },
        ],
        shiny: {
          id: 4,
          category: "shiny",
          image:
            "https://www.pokepedia.fr/images/b/b8/Sprite_004_chromatique_EB.png",
          catched: true,
          type: [
            {
              name: "Feu",
            },
          ],
        },
      },
    ],
  },
  {
    id: 3,
    name: "Carapuce",
    nationalNumber: "007",
    appearances: [
      {
        id: 5,
        category: "normal",
        image: "https://www.pokepedia.fr/images/7/75/Sprite_007_EB.png",
        catched: false,
        type: [
          {
            name: "Eau",
          },
        ],
        shiny: {
          id: 6,
          category: "shiny",
          image:
            "https://www.pokepedia.fr/images/f/fd/Sprite_007_chromatique_EB.png",
          catched: true,
          type: [
            {
              name: "Eau",
            },
          ],
        },
      },
    ],
  },
  {
    id: 4,
    name: "Ponyta",
    nationalNumber: "077",
    appearances: [
      {
        id: 7,
        category: "normal",
        image: "https://www.pokepedia.fr/images/5/53/Sprite_077_EB.png",
        catched: true,
        type: [
          {
            name: "Feu",
          },
        ],
        shiny: {
          id: 8,
          category: "shiny",
          image:
            "https://www.pokepedia.fr/images/2/2c/Sprite_077_chromatique_EB.png",
          catched: false,
          type: [
            {
              name: "Feu",
            },
          ],
        },
      },
      {
        id: 9,
        category: "galar",
        image: "https://www.pokepedia.fr/images/c/c9/Sprite_077_Galar_EB.png",
        catched: false,
        type: [
          {
            name: "Psy",
          },
        ],
        shiny: {
          id: 10,
          category: "shiny",
          image:
            "https://www.pokepedia.fr/images/9/91/Sprite_077_Galar_chromatique_EB.png",
          catched: true,
          type: [
            {
              name: "Psy",
            },
          ],
        },
      },
    ],
  },
]);
</script>

<template>
  <div class="flex flex-wrap flex-row justify-center gap-2">
    <PokemonCard
      v-for="pokemon in pokemons"
      :key="pokemon.id"
      :pokemon="pokemon"
    />
  </div>
</template>
