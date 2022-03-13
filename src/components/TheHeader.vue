<script setup>
import { ref } from "vue";
import { RouterLink } from "vue-router";

const openMenu = ref(false);

function toggleBurgerMenu() {
  openMenu.value = !openMenu.value;
}
</script>

<template>
  <nav class="shadow-xl sticky top-0 z-50">
    <div class="container flex justify-between px-4 py-8 mx-auto bg-white">
      <div>
        <h3 class="text-2xl font-medium">Pokédex</h3>
      </div>
      <div class="hidden space-x-8 md:flex">
        <RouterLink to="/">Hisui</RouterLink>
        <RouterLink to="/login">Se connecter</RouterLink>
      </div>
      <div class="flex md:hidden cursor-pointer" v-on:click="toggleBurgerMenu">
        <div class="space-y-2">
          <span class="block w-8 h-0.5 bg-black"></span>
          <span class="block w-8 h-0.5 bg-black"></span>
          <span class="block w-8 h-0.5 bg-black"></span>
        </div>
      </div>
    </div>
    <div
      class="container flex flex-col px-4 py-8 mx-auto space-y-2 md:hidden bg-white"
      :class="{ hidden: !openMenu }"
    >
      <RouterLink class="place-self-center" to="/">Hisui</RouterLink>
      <RouterLink class="place-self-center" to="/login"
        >Se connecter</RouterLink
      >
    </div>
  </nav>
</template>

<style>
.router-link-exact-active {
  font-weight: bold;
  border-bottom: 2px solid black;
}
</style>
