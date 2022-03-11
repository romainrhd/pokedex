<script setup>
import { ref } from "vue";
const active = ref(false);
function changeInput() {
  active.value = !active.value;
}
</script>

<template>
  <div class="flex flex-col m-auto bg-red-600 border border-black rounded">
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
          <div class="bg-yellow-300 p-1 rounded-3xl border border-black"></div>
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
        <label for="login">Login</label>
        <input
          id="login"
          class="rounded p-2"
          type="text"
          name="login"
          @keypress="changeInput"
        />
      </div>
      <div class="flex flex-col p-3">
        <label for="password">Mot de passe</label>
        <input
          id="password"
          class="rounded p-2"
          type="password"
          name="password"
          @keypress="changeInput"
        />
      </div>
      <div class="flex flex-col p-3">
        <button class="rounded bg-green-500 py-4">Se connecter</button>
      </div>
    </div>
  </div>
</template>
