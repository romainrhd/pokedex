<script setup>
import { ref } from "vue";
import { RouterLink } from "vue-router";
import IconPokeball from "@/components/icons/IconPokeball.vue";

const active = ref(false);
function changeInput() {
  active.value = !active.value;
}
</script>

<template>
  <div class="flex flex-col m-auto">
    <RouterLink class="flex justify-center" to="/">
      <IconPokeball class="w-14" />
    </RouterLink>
    <h3 class="flex justify-center mb-3">Se connecter à mon Pokédex</h3>
    <div class="bg-red-600 border border-black rounded">
      <div class="flex m-auto space-x-1">
        <div
          class="p-4 m-2 rounded-3xl border-2"
          :class="active ? 'bg-blue-600' : 'bg-blue-500'"
        ></div>
        <div class="flex space-x-1 pt-0.5 pl-2 mt-2">
          <div>
            <div class="bg-red-600 p-1 rounded-3xl border border-black"></div>
          </div>
          <div>
            <div
              class="bg-yellow-300 p-1 rounded-3xl border border-black"
            ></div>
          </div>
          <div>
            <div class="bg-green-400 p-1 rounded-3xl border border-black"></div>
          </div>
        </div>
        <div class="px-16"></div>
      </div>
      <div class="border-b border-black"></div>
      <div class="flex flex-col h-80">
        <div class="flex flex-col p-3">
          <label for="login" class="mb-2 text-white">Login</label>
          <input
            id="login"
            class="rounded p-2"
            type="text"
            name="login"
            @keypress="changeInput"
          />
        </div>
        <div class="flex flex-col p-3">
          <label for="password" class="mb-2">Mot de passe</label>
          <input
            id="password"
            class="rounded p-2"
            type="password"
            name="password"
            @keypress="changeInput"
          />
        </div>
        <div class="flex flex-col p-3">
          <button class="rounded-full bg-blue-600 py-1 text-white">
            Se connecter
          </button>
        </div>
        <div class="flex p-3 justify-center">
          <a href="#">Mot de passe perdu ?</a>
        </div>
      </div>
    </div>
  </div>
</template>
